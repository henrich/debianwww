========================================================================
Old distribution archives
========================================================================

.. _debian-archive:

debian-archive
========================================================================

If you need to access one of the old distributions of Debian, you can
find them at the `Debian Archives Site <http://archive.debian.org/debian/>`_ 
and its mirrors.

The following is a list of mirrors that include the archive:

#include "$(ENGLISHDIR)/distrib/archive.mirrors"
<archivemirrors>



Archived codename and its version
========================================================================

Releases are stored by their codenames under the :file:`dists/` directory.


.. list-table:: Archived list

   * - Version
     - Codename
     - Binary?

   * - Debian6.0
     - :ref:`squeeze`
     - Yes

   * - Debian5.0
     - Lenny
     - Yes

   * - Debian4.0
     - Etch
     - Yes

   * - Debian3.1
     - Sarge
     - Yes

   * - Debian3.0
     - Woody
     - Yes

   * - Debian2.2
     - Potato
     - Yes

   * - Debian2.1
     - Slink
     - Yes

   * - Debian2.0
     - Hamm
     - Yes

   * - Debian1.3
     - Bo
     - Yes

   * - Debian1.2
     - Rex
     -  

   * - Debian1.1
     - Buzz
     -  


If you are using APT the relevant sources.list entries are like::

  deb http://archive.debian.org/debian/ Debian-6.0 main contrib non-free

  deb http://archive.debian.org/debian/ bo bo-unstable main contrib non-free


You can search packages in the old distributions at http://archive.debian.net .


.. _non-us-archive:

debian-non-US archive
========================================================================

In the past, there was software packaged for Debian that could not be
distributed in the US (and other countries) due to restrictions on export
of cryptography or software patents. Debian maintained a special archive
called the `non-US` archive.

These packages were incorporated into the main archive in Debian 3.1
and the debian-non-US archive is discontinued; it is actually
*archived* now, incorporated into the archive.debian.org archives.

They are still available from the archive.debian.org and its mirror.

Available access methods are:

  `http://archive.debian.org/debian-non-US/ <http://archive.debian.org/debian-non-US/>`_

  `ftp://archive.debian.org/debian-non-US/ <ftp://archive.debian.org/debian-non-US/>`_

  rsync://archive.debian.org/debian-non-US/ (limited)


To use these packages with APT, the relevant sources.list entries are like::

  deb http://archive.debian.org/debian-non-US/ woody/non-US main contrib non-free
  deb-src http://archive.debian.org/debian-non-US/ woody/non-US main contrib non-free

