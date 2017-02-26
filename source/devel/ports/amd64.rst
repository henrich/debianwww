================================================================================
AMD64 Port
================================================================================

Debian on AMD64
================================================================================

This page is meant to assist users and Debian developers running
Debian GNU/Linux on the AMD64 architecture. Here, you will find
information about the current status of the port, which machines are
publicly accessible by developers, where to discuss development of
the port, where to get further information about Debian porters, and
pointers to more information.

Current Status
--------------------------------------------------------------------------------
AMD64 has been an officially supported Debian architecture since the
release of Debian 4.0 (etch).

The port consists of a kernel for all AMD 64bit CPUs with *AMD64* 
extension and all Intel CPUs with *Intel 64* extension, and a common 
64bit userspace.

A complete 64bit userland
--------------------------------------------------------------------------------
The AMD64 port is thoroughly 64bit, allowing the user to benefit from all 
advantages this architecture has compared to i386::

 * no memory segmentation into low and high memory
 * up to 128TiB virtual address space per process (instead of 2GiB)
 * 64TiB physical memory support instead of 4GiB (or 64GiB with the PAE extension)
 * 16 general purpose registers in the CPU instead of 8
 * gcc defaults to SSE2 math instead of 387 FPU
 * gcc omits frame-pointers by default at -O2
 * compilation time optimization uses a common base for AMD64/Intel 64
   instead of legacy i386 cruft
 * memory pages are not executable by default

Native execution of legacy 32bit binaries is supported by the kernel, and 
core libraries are provided by the ia32-libs package.


.. i386support::

Minimalistic AMD64 runtime support for i386
--------------------------------------------------------------------------------
The official i386 distribution actually includes minimalistic AMD64 
support, consisting of a 64bit kernel, a toolchain able to create 64bit binaries 
and the amd64-libs package to run third-party amd64 binaries with native shared
libraries.


Links
--------------------------------------------------------------------------------

 * Mailing list: Discussions and development for this port take place on the
   `debian-amd64 <https://lists.debian.org/debian-amd64/>`_ list.

 * the `debian-amd64 Wiki <https://wiki.debian.org/DebianAMD64>`_

 * All Debian members can port packages using the Debian
   `porterbox machines <https://db.debian.org/machines.cgi>`_

 * The `debian-amd64 howto and FAQ <https://alioth.debian.org/docman/view.php/30192/21/debian-amd64-howto.html>`_ 
   (Historical, deadlink)

 * `CVS Repository <https://anonscm.debian.org/viewvc/debian-amd64/>`_
   (Historical)

 * the `debian-amd64 Alioth project <https://alioth.debian.org/projects/debian-amd64/>`_
   (Historical)



