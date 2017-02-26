.. include:: /define.txt

==========================================================================
Debian package
==========================================================================

Search package
==========================================================================

#include "$(ENGLISHDIR)/distrib/search_contents-form.inc"

There are shortcuts for some searches available:

 * ``https://packages.debian.org/<pakage name>`` for the search on package names.
 * ``https://packages.debian.org/src:<pakage name>``
   for the search on source package names.


Search the contents of packages
==========================================================================

#include "$(ENGLISHDIR)/distrib/search_contents-form.inc"

A shortcut available::

  https://packages.debian.org/file:<path>

for the search for paths ending in the keyword.
This search engine allows you to search the contents of Debian
distributions for any files (or just parts of file names) that are
part of packages.



Introductory notes
==========================================================================
Debian has packages in three ``repository`` and several ``distribution`` (version)

repository
--------------------------------------------------------------------------

.. _main:

main
^^^^^^^^^^^^
    All packages that are included in the official Debian distribution are
    free according to the :ref:`DFSG` .
    This assures free use and redistribution of the packages and their complete 
    source code. The official Debian distribution is what is contained
    in the *main* section of the Debian archive.

.. _contrib:

contrib
^^^^^^^^^^^^
    Packages in this area are freely licensed by the copyright
    holder but depend on other software that is non-free one.

.. _non-free:

non-free
^^^^^^^^^^^^
    Packages in this area have some onerous license condition
    restricting use or redistribution of the software.

As a service to our users, we also provide packages in separate repositories
(*contrib* and *non-free*) that cannot be included in the *main* distribution 
due to either a restrictive license or legal issues.


distribution
--------------------------------------------------------------------------

.. _stable:

stable
^^^^^^^^^^^^
  This is the latest official release of the Debian
  distribution. This is stable and well tested software, which changes
  only if major security or usability fixes are incorporated.

  Now *stable* is Debian |stable version| |stable codename|

.. _testing:

testing
^^^^^^^^^^^^
  This area contains packages that are intended to become part of the next
  stable distribution.  There are strict criteria a package in unstable (see
  below) must obey before it can be added to testing.
  Note that *testing* does not get the timely security updates
  :ref:`from the security team <how-is-security-handled-for-testing>`.

unstable  
^^^^^^^^^^^^
  This area contains the most recent packages in Debian. Once a
  package has met our criterion for stability and quality of packaging,
  it will be included in *testing*. *unstable* is also not supported
  :ref:`by the security team <how-is-security-handled-for-unstable>`.

  Packages in unstable are the least tested and may contain
  problems severe enough to affect the stability of your system.
  Only experienced users should consider using this distribution.

  See the `unstable distribution pages <../releases/unstable/>` 
  for more information.

.. _experimental:

experimental
^^^^^^^^^^^^
  
.. _oldstable:

oldstable
^^^^^^^^^^^^
  Now *oldstable* is |oldstable version| |oldstable codename|


oldoldstable
^^^^^^^^^^^^
  Now *oldoldstable* is |oldoldstable version| |oldoldstable codename|


