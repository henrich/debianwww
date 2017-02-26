
.. toctree::
   nonvuln

====================================================================================
Key Rollover - packages that are not vulnerable
====================================================================================

The software listed on this page uses cryptographic keys, but is 
**not vulnerable** to the :doc:`OpenSSL vulnerability <index>`,
as OpenSSL is not used to generate or exchange its keys.

.. contents:

ckermit
====================================================================================
Debian's version doesn't enable crypto support due to licensing 
issues, and is so not affected.


GnuPG
====================================================================================
GnuPG does not use OpenSSL, so gpg keys are not impacted by the
vulnerability. However, keys that were stored on systems that could be
attacked by using weak SSH keys, or other means, could be indirectly
exposed, and gpg passphrases sent over ssh connections using weak SSH
keys could be potentially exposed.


Iceweasel
====================================================================================
The Iceweasel ("firefox") web browser functionality for generating X509 
public/private keypairs (certificates) is not affected by this
vulnerability. Iceweasel uses nss, a different cryptography engine.


MySQL
====================================================================================
Due to licensing issues, the Debian version of MySQL uses the
yassl copy included in MySQL and is not affected.

