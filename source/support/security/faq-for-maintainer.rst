====================================================================
Debian security FAQ for package maintainers
====================================================================

What am I supposed to do with a security problem in one of my packages?
==========================================================================================

If you learn of a security problem, either in your package or
someone else's please always contact the `security team <team@security.debian.org>`_. 
They keep track of outstanding security problems, can help maintainers with
security problems or fix problems on their own, are responsible for
sending out security advisories and maintaining
security.debian.org.

The `Debian Developer's Reference <https://www.debian.org/docs/developers-reference/pkgs.html#bug-security>`_
has complete instructions on what to do.

It's particularly important that you don't upload to any other
distribution other than unstable without prior agreement by the
security team, because bypassing them will cause confusion and more
work.


I've got a bugfix, can I upload to security.debian.org directly?
==========================================================================================

No, you can't.  The archive at security.debian.org is maintained
by the security team, who have to approve all packages.  You should
instead send patches or proper source packages to the `security team <team@security.debian.org>`_.
They will be reviewed by the  security team and eventually uploaded, either with
or without modifications.

The `Debian Developer's Reference <https://www.debian.org/docs/developers-reference/pkgs.html#bug-security>`_
has complete instructions on what to do.


I've got a bugfix, can I upload to proposed-updates instead?
==========================================================================================

Technically speaking, you can.  However, you should not do this,
since this interferes badly with the work of the security team.
Packages from security.debian.org will be copied into the
proposed-updates directory automatically.  If a package with the
same or a higher version number is already installed into the
archive, the security update will be rejected by the archive
system.  That way, the stable distribution will end up without a
security update for this package instead, unless the "wrong"
packages in the proposed-updates directory were rejected.  Please contact the
security team instead and include all details of the vulnerability
and attach the source files (i.e. :file:`diff.gz` and :file:`dsc` files) to your mail.

The `Debian Developer's Reference <https://www.debian.org/docs/developers-reference/pkgs.html#bug-security>`_
has complete instructions on what to do.

I'm pretty sure my packages are fine, how can I upload them?
==========================================================================================

If you are very sure that your packages don't break anything, that the
version is sane (i.e. greater than the version in stable and less than the
version in testing/unstable), that you didn't change the behaviour of the
package, despite the corresponding security problem, that you compiled it
for the correct distribution (that is ``oldstable-security`` or
``stable-security``), that the package contains the original
source if the package is new on security.debian.org, that you can confirm
the patch against the most recent version is clean and only touches the
corresponding security problem (check with ``interdiff -z`` and
both :file:`.diff.gz` files), that you have proofread the patch at
least thrice, and that ``debdiff`` doesn't display any changes,
you may upload the files into the incoming directory
ftp://security-master.debian.org/pub/SecurityUploadQueue on the
security.debian.org directly.  Please send a notification with all details
and links to `security team <team@security.debian.org>`_ as well.


What is the scope of proposed-updates?
==========================================================================================

This directory contains packages which are proposed to enter the
next revision of Debian stable.  Whenever packages are uploaded by
a maintainer for the stable distribution, they end up in the
proposed-updates directory.  Since stable is meant to be stable, no
automatic updates are made.  The security team will upload fixed
packages mentioned in their advisories to stable, however they will
be placed in proposed-updates first.  Every couple of months the
:ref:`Stable Release Manager` checks the list of packages in
proposed-updates and discusses whether a package is suited for
stable or not.  This is compiled into another stable point release
(e.g. 8.5 or 8.6).  Packages that don't fit will probably be
rejected and dropped from proposed-updates as well.

Note that the packages uploaded by maintainers (not by the security team)
in the proposed-updates/ directory are **not** supported by the security
team.
