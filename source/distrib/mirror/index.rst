.. Debian website restructuring documentation master file, created by
   sphinx-quickstart on Mon Jan  2 22:41:42 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

===============================================================
Debian mirrors
===============================================================

.. toctree::
   :maxdepth: 2


What is mirror in Debian?
===============================================================
Debian is distributed all around the world using 
`mirrors <http://foldoc.org/mirror+site>`_ in order to provide 
users with better access to our archive and to reduce
the load on our servers.

Selecting mirror
===============================================================
TBD


Public Debian mirrors and its sponsors
-------------------------------------------------------------
See :doc:`mirror-list`.


Official Debian mirrors and its sponsors
-------------------------------------------------------------
Official Debian archive mirrors are the best advertised and 
most used sites; the face of Debian for most people. 
They get an address of the form
ftp.\ *<country code>*\.debian.org (e.g. ftp.us.debian.org). 
See :doc:`official-mirror`.


Mirror redirector service
--------------------------------------------------------------
If you don't know which mirror to use or your system moves around a lot,
you can use the `mirror redirector service <https://deb.debian.org/>`_
in your `/etc/apt/sources.list <http://manpages.debian.org/man/5/sources.list>`_ file.

.. code-block:: none

  deb http://deb.debian.org/debian sid main

It dynamically redirects package download requests to the best mirror
available based on a number of factors such as mirror availability,
location, architecture and freshness.

Mirror information
=============================================================

Public mailing lists about Debian mirrors

  `debian-mirrors-announce <https://lists.debian.org/debian-mirrors-announce/>`_
    We encourage **all mirror maintainers to subscribe to the announcement list** as
    it will be used for any important announcements. This list is moderated and will
    receive only a low amount of traffic. 

  `debian-mirrors <https://lists.debian.org/debian-mirrors/>`_
    This mailing list is meant for general discussion and is open to all.

Public IRC channel

  #debian-mirrors on ``irc.debian.org``


Debian mirrors have timestamp files we use to determine how recently
they have been updated. Here are some statistics the mirror maintainers
provide:

 * http://mirror.debian.org/status.html
 * http://ftp.de.debian.org/dmc/today/


Setup new mirror
=============================================================
Debian mirrors are maintained by volunteers, so
if you are in a position to donate disk space and network connectivity,
:doc:`setup new mirror <setup-mirror>` and :doc:`submit it<submit-mirror>`
to make Debian more accessible.


Contact
=============================================================

If you have any questions that aren't answered on these web pages, 
you can contact us at

 * `debian-mirrors <https://lists.debian.org/debian-mirrors/>`_ public mailing list
 * IRC #debian-mirrors on ``irc.debian.org``.
 * mirrors@debian.org

