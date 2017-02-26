====================================================================
Security Information
====================================================================

Debian takes security very seriously. We handle all security problems
brought to our attention and ensure that they are corrected within
a reasonable timeframe.
Many advisories are coordinated with other free software vendors
and are published the same day a vulnerability is made public.

.. "reasonable timeframe" might be too vague, but we don't have 
   accurate statistics. For older (out of date) information and data
   please read:
   https://www.debian.org/News/2004/20040406  [ Year 2004 data ]
   and (older)
   https://people.debian.org/~jfs/debconf3/security/ [ Year 2003 data ]
   https://lists.debian.org/debian-security/2001/12/msg00257.html [ Year 2001]
   If anyone wants to do up-to-date analysis please contact me (jfs)
   and I will provide scripts, data and database schemas.

.. we also have a <a href="audit/">Security Audit</a> team that reviews
   the archive looking for new or unfixed security bugs.

Experience has shown that "security through obscurity" does not work. Public
disclosure allows for more rapid and better solutions to security problems.

.. In that vein, this page addresses Debian's status with respect to various known
   security holes, which could potentially affect Debian.


Recent Security Advisories
====================================================================

You can get security advisories via :doc:`several ways <stay-informed>`.


Keeping your Debian system secure
====================================================================
You can use `apt <https://packages.debian.org/stable/admin/apt>`_ 
to easily get the latest security updates.

 #. In your :file:`/etc/apt/sources.list` file, set below line.::

      deb http://security.debian.org/ <current_release_name>/updates main

 #. Execute ``apt update && apt upgrade`` to download and apply
    the pending updates.

Contact Information
===============================================================================

.. note::

  Please read the :doc:`Debian security FAQ <faq>` before contacting us,
  your question may well be answered there already!

  The :ref:`contact information is in the FAQ <security-contact>` as well.


Links
===============================================================================

 * The `Debian Security Tracker <https://security-tracker.debian.org/>`_
   collects all information about the vulnerability status of Debian packages,
   and can be searched by CVE name or by package.

 * The security archive is signed with the
   `Debian archive signing keys <https://ftp-master.debian.org/keys.html>`_.
   You can check the integrity of packages with it. Detailed instruction on
   how to do it, see
   `Securing Debian manual <:$HOME/doc/manuals/securing-debian-howto/ch7#s-deb-pack-sign>`

 * About Debian's security standardization efforts

   * About :doc:`cve-compatibility` and :doc:`cross references <crossreferences>`
   * Debian is represented in the Board of the 
     `Open Vulnerability Assessment Language Project <https://oval.mitre.org/>`_

.. Debian distributions are not vulnerable to all security problems. 
