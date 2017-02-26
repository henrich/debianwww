=================================================
Setting up a Debian archive mirror
=================================================

Whether to mirror
=================================================

While we appreciate all new mirrors, every prospective mirror maintainer
should make sure that they can answer these questions before trying to
start their own mirror:

 * **Is a mirror the right choice?** Sometimes people mistakenly start a mirror,
   when they actually want to run a caching proxy,
   such as `apt-cacher-ng <https://packages.debian.org/apt-cacher-ng>`_.
 * **Is a mirror necessary at my location?** Maybe there are already mirrors nearby.
 * **Do I have the resources to host a mirror?** Mirrors take up considerable
   :doc:`mirror-size` and bandwidth, one has to be able to commit to the cost.

What to mirror
=================================================

Debian package archive

   * **debian/** archive is used to install Debian over
     the network, to build CDs from (with jigdo), and to upgrade already
     installed systems.

   * **debian-security/** archives contain the security updates released by
     the Debian security team. It sounds interesting to everyone, but since the
     security updates are sporadic, one would have to mirror it very often to be
     up to date (or use :doc:`push-mirroring`)
     so **we do not recommend it**.
     Debian makes every effort to maintain the high availability of
     ``security.debian.org`` instead.

   * **debian-archive/** contains the true *archive*, the old and obsolete
     versions of Debian, its security update was already terminated.
     It will generally be interesting only to a small segment of users, 
     so **we do not recommend it**. For more detail, see `debian-archive`.


Debian install image archive

   * **debian-cd/** is an archive that isn't identical across all the different
     mirror servers. On some sites it contains jigdo templates to build CD images
     from (used in combination with files from debian/), on some it contains
     already built CD images, and on some sites both.

     Please see the page for `mirroring the CD images <$(HOME)/CD/mirroring/>`_
     for further information on this.


Please see :doc:`mirror-size` page for more precise information about mirror sizes.


Where to mirror from
=================================================

The :doc:`official-mirror` are meant to be a good place to mirror from. 
Any of the servers in the :doc:`mirror-list` that have the tags ``Type: Push-Primary`` 
or ``Type: Push-Secondary`` should be good to mirror from.
Please use one that is close to you both network-wise and geographically.

There is no real difference between different *Push-Primary*
mirror servers as far as mirroring is concerned. On the other
hand, if many people use ftp.debian.org (and unfortunately, they do), this
needlessly wastes the donated bandwidth.

.. note::

  Many people seem to think that ``ftp.debian.org`` is the
  canonical location of Debian packages and that it will be best for them
  to mirror from that site. This is *not true*.

  ``ftp.debian.org`` is merely one of several servers that get
  updated from an internal Debian server. That address is presently located
  on a single server, and it still exists mainly for
  backwards compatibility.


.. note::

  Mirror administrators in the United States should mirror from
  ftp.us.debian.org (the official mirror address from the US, which is a
  Push-Primary mirror). But, since that address is also a round-robin alias
  for several machines, it usually makes sense to determine which of the
  components is the best and then mirror from that particular one.

  The upside of doing that is that it avoids the risk of failures
  when performing a two-stage rsync (different stages might end up on
  different machines during time windows where they have different data,
  causing a race condition). The downside is that it concentrates on
  a single site the performance of which may vary, but that is currently
  inherent to our mirror network in general.


.. _ftpsync:

How to mirror with ftpsync
=================================================

We recommend to use the **ftpsync scriptset** to mirror the archive.

 * tarball from https://ftp-master.debian.org/ftpsync.tar.gz
 * git repository: :kbd:`git clone https://ftp-master.debian.org/git/archvsync.git`

Follow the :file:`README` file included to set up mirroring.


Partial mirroring
------------------------------------------------

Considering the already :doc:`mirror-size`, some people prefer to mirror 
only parts of it they need. 
*If you want to exclude something, you should exclude architectures*.
With the recommended :ref:`ftpsync <ftpsync>`, this can be done by
editing the **ARCH_EXCLUDE** variable.

We strongly advise against excluding the :file:`project/`, :file:`doc/`
and other subdirectories. Usually these are minor in size and yet useful to
users.
Especially :file:`project/trace` helps very much if there are any mirror issues.

It is possible to use other specially written scripts, but they are
usually not necessary, and not recommended for official mirrors.


Push-triggered mirroring
------------------------------------------------

:doc:`push-mirroring` is a form of mirroring that we have developed
to minimize the time it takes for changes to the archive to reach mirrors.
An upstream mirror uses an SSH trigger to tell the downstream mirror to
update itself. The "pushing" is usually limited to a secure trigger
that takes no variable data, so the rest of the mirroring process is
simply ""pull"" like with a cron job.

Push mirroring is necessary to keep multiple servers in synchronization
(such as servers in DNS round-robin aliases like ``ftp.us.debian.org``),
and we use it for our first and second tier mirrors. But as this method
requires a bit more effort to set it up, it isn't commonly done for
"private" mirrors.


When to mirror
=================================================
The main archive gets updated 4 times a day.
The mirrors commonly start updating around 3:00, 9:00, 15:00 and 21:00 (all times UTC),
but these are never fixed times and you should not fixate your mirror on them.

Your mirror should update a few hours after one of the main archive
mirror pulses.
You should check if the site you're mirroring from leaves a time stamp
file in their :file:`project/trace/` subdirectory. The time stamp file
will be named like that site, and it will contain the completion time of
their last mirror update. Add a couple of hours to that time (to be safe)
and mirror then.

**It is essential that your mirror is in sync with the main archive**. 
A minimum of 4 updates per 24 hours will ensure that your mirror is a true 
reflection of the archive. Please understand that mirrors that are not in sync 
with the main archive will not be listed in the official mirrors listing.

The easiest way to automatically have the mirror run every day is to use
cron. See :manpage:`crontab(1)` for details.

Note that if your site is being triggered with :doc:`a push mechanism <push-mirroring>`, 
then you don't need to worry about any of this.


Recommended additional settings
=================================================

If you are going to make the Debian mirror available through HTTP, please
add the following settings to your Apache configuration (presuming, of
course, you will use Apache), within the ``Directory /path/to/your/debian/mirror`` 
block, where :file:`/path/to/your/debian/mirror` should be the actual name of 
the directory where you keep the mirror::

  <pre>
    Options +Indexes +SymlinksIfOwnerMatch
    IndexOptions NameWidth=* +SuppressDescription
  </pre>

This enables the directory indices and makes sure that following
symlinks will work. The file names in the directory indices won't be truncated,
and (mostly nonexistent) descriptions won't be shown.


How to add a mirror to public mirror list
=================================================
If you would like to have your mirror listed on public mirrors list please: 

 * Ensure that your mirror synchronizes 4 times per 24 hours with the archive
 * Ensure that your mirror includes the source files for the architectures the 
   mirror carries

Once the mirror is set up, it should be registered with :doc:`submit-mirror`
in order to get included in :doc:`mirror-list` .


Misc mirror notes 
=================================================
 * The mirroring protocol which we strongly recommend is :command:`rsync`.

 * Please do not mirror Debian using :command:`wget` and other tools based on FTP.
   They may seem to work well, but will have numerous issues
   (they can't detect hard links, it's harder to make partial mirrors, etc).

 * If you do use your own scripts, the minimal functionality that must be 
   supported is as follows:

   * MUST perform a 2-stage sync
     The archive mirroring must be done in 2 stages. The first rsync run
     must ignore the index files.  The correct exclude options for the 
     first rsync run are::

       --exclude Packages* --exclude Sources* --exclude Release* --exclude InRelease --exclude i18n/* --exclude ls-lR*

     The first stage must not delete any files.
     The second stage should then transfer the above excluded files and
     delete files that no longer belong on the mirror.

     Rationale: if archive mirroring is done in a single stage, there will be
     periods of time during which the index files will reference files not
     yet mirrored.

   * MUST not ignore pushes while running (for :doc:`push-mirroring`).
     If a push is received during a run of the mirror sync, it MUST NOT
     be ignored.  The whole synchronization process must be rerun.

     Rationale: most implementations of Debian mirror scripts will leave the
     mirror in an inconsistent state in the event of a second push being
     received while the first sync is still running.  It is likely that in
     the near future, the frequency of pushes will increase.

   * Run rsync with at least these options::

       --recursive --times --links --hard-links --delete

   * If you have extra disk space, also use the ``--delete-after``
     option to avoid some of the temporary update problems.

   * After rsync is done mirroring, add a time stamp file to the
     :file:`project/trace/` subdirectory of the Debian mirror
     named after your server. This means running:

       :kbd:`date -u .../debian/project/trace/your.server`
  
     after your daily rsync is finished.

   * We strongly advise against excluding the :file:`project/`, :file:`doc/`
     and other subdirectories. Usually these are minor in size and yet useful to
     users.
     Especially :file:`project/trace` helps very much if there are any mirror issues.


