===========================================
List of Debian Official mirror
===========================================

Official Debian archive mirrors get an address of the form
ftp.country code.debian.org. These are the best advertised
and most used sites; the face of Debian for most people.


List of official Debian archive mirrors
=============================================================

<officialarchivemirrors>


Criteria
=============================================================

To become an official mirror, it should meet the following criteria:

 #. The site should be reliable and be up 24 hours a day. The machine should
    not be heavily loaded.
 #. The **whole** Debian archive should be mirrored.
 #. Disk space commitments (with room for expansion) &mdash; see the
    :doc:`mirror-size`.
 #. The mirror should be updated with :ref:`ftpsync script <ftpsync>`.
 #. :doc:`push-mirroring` needs to be set up; feel free to contact us
    to get in touch with the maintainer of another mirror.
 #. It should have a decent connectivity (relative to the respective country).
    Bandwidth equivalent to a 100Mbps connection or better is preferred;
    note that for developed countries, this minimum is much higher.
 #. The routers in front of the server shouldn't have any global
    access bans or major limitations of bandwidth.
 #. The server needs to be able to sustain the traffic, i.e. have
    reasonable limits on the HTTP, FTP and rsync daemons, including
    tuning the maximum number of connections in general and the maximum
    number of connections from a single IP.
 #. The mirror hierarchy should be available under :kbd:`/debian`
    Rationale: for consistency between sites - you may simply
    place a symlink if you want to keep the mirror somewhere else, or
    set up a virtual host.
 #. The mirror should be made available at least via these protocols:       

       * HTTP (\http://your.server/debian/\)

           HTTP is used because with HTTP/1.1 transfers have the
           potential of being more efficient than with FTP.
 
       * FTP (\ftp://your.server/debian/\)

           FTP is the most senior protocol, and still very widely used.

       * rsync (\rsync://your.server::debian/\)

           Rsync is the preferred method of mirroring, and one of
           the main functions of an official mirror is to help the
           proliferation of secondary mirrors.

 #. The mirror should be registered as public mirror 
    (using our :doc:`submit mirror information form <submit-mirror>`).


Please note that these are *just guidelines*, but we will be more likely to
accept your site as an official mirror if the above conditions are met.
It is also generally desirable for the site to have a history of working
as described above.


Process
======================================================
Official mirrors are hosted by selected persons or groups who donate
their resources as a service to all Debian users from their country.

Debian depends on information provided by users and mirror maintainers
in order to make decisions about the mirror hierarchy. All constructive
input regarding existing or missing official mirrors is welcome at
mirrors@debian.org or at `debian-mirrors mailing list <https://lists.debian.org/debian-mirrors/>`_.


If there isn't already an ftp.*country code*.debian.org for
your country, any mirror maintainer can apply for their site to become
the official one, provided it meets the criteria outlined above.

In countries where there is already an official mirror assigned,
it is still possible to set up more official sites, but only if there
is demand for such a thing. In large countries, like the US, and countries
with more than one major backbone that aren't well connected,
like Australia, it is even a good idea.

Usually, the first site will be given the aliases
ftp.*country code*.debian.org and ftp1.*country code*.debian.org.
Future sites will simply be given an alias of the second type
with the number incremented appropriately.

All applications for official sites, including exact information on
bandwidth consumption and any limits, should be sent to
mirrors@debian.org .

