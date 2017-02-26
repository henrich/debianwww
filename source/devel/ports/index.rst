=========================================================================
Ports
=========================================================================

Introduction
=========================================================================

As most of you know, `Linux <https://www.kernel.org/>`_
is just a kernel.  And, for a long time,
the Linux kernel ran only on the Intel x86 series of machines, from
the 386 up.

However, this is no longer true, by any means.  The Linux kernel has
now been ported to a large, and growing, list of architectures.
Following close behind, we have ported the Debian distribution to
these architectures.  In general, this is a process with a sticky
start (as we get libc and the dynamic linker working smoothly), and
then a relatively routine, if lengthy job, of attempting to recompile
all our packages under the new architectures.

Debian is an operating system (OS), not a kernel (actually, it is more
than an OS since it includes thousands of application programs). Accordingly,
while most Debian ports are based on Linux, there also are ports based on the
`FreeBSD <https://www.freebsd.org/>`_ and 
`Hurd <https://www.gnu.org/software/hurd/>`_ kernels.


.. important::
 This is a page in progress.  Not all ports have
 pages yet, and most of them are on external sites.  We are working on
 collecting information on all ports, to be mirrored along with the Debian
 website.
 More ports may be `listed on the wiki <https://wiki.debian.org/CategoryPorts>`_.

Ports list
=========================================================================

List of official ports
-------------------------------------------------------------------------
.. list-table:: List of official ports (release architecture)
   :widths: 10 10 70 10
   :header-rows: 1

   * - Port
     - Architecture
     - Description
     - Status

   * - :doc:`amd64 <amd64>`
     - 64-bit PC (amd64)
     - First officially released with Debian 4.0. Port to 64-bit x86
       processors. The goal is to support both 32-bit and 64-bit userland on this
       architecture. This port supports AMD's 64-bit Opteron, Athlon and Sempron
       processors, and Intel's processors with Intel 64 support, including the
       Pentium D and various Xeon and Core series.
     - `released <https://www.debian.org/releases/stable/amd64/release-notes/>`_

   * - :doc:`arm64 <arm>`
     - 64-bit ARM (AArch64)
     - Version 8 of the ARM architecture included AArch64, a new 64-bit
       instruction set. Since Debian 8.0, the arm64 port has been included in
       Debian to support this new instruction set on processors such as the
       Applied Micro X-Gene, AMD Seattle and Cavium ThunderX.
     - `released <https://www.debian.org/releases/stable/arm64/release-notes/>`_

   * - :doc:`armel <arm>`
     - EABI ARM
     - The oldest of the current Debian ARM ports supports little-endian
       ARM CPUs compatible with the v4t instruction set.
     - `released <https://www.debian.org/releases/stable/armel/release-notes/>`_

   * - :doc:`armhf <arm>`
     - Hard Float ABI ARM
     - A lot of modern 32-bit ARM boards and devices ship with a floating-point
       unit (FPU), but the Debian armel port doesn't take much advantage
       of it. The armhf port was started to improve this situation and also take
       advantage of other features of newer ARM CPUs. The Debian armhf port
       requires at least an ARMv7 CPU with Thumb-2 and VFP3-D16 floating point
       support.
     - `released <https://www.debian.org/releases/stable/armhf/release-notes/>`_

   * - :doc:`i386 <i386>`
     - 32-bit PC (i386)
     - The first architecture, and not strictly a port. Linux was originally
       developed for the Intel 386 processors, hence the short name. Debian
       supports all IA-32 processors, made by Intel (including all Pentium
       series and recent Core Duo machines in 32-bit mode), AMD (K6, all Athlon
       series, Athlon64 series in 32-bit mode), Cyrix and other
       manufacturers.
     - `released <https://www.debian.org/releases/stable/i386/release-notes/>`_

   * - :doc:`mips <mips>`
     - MIPS (big-endian mode)
     - First officially released with Debian 3.0. Debian is being ported to
       the MIPS architecture which is used in SGI machines (debian-mips —
       big-endian) and Digital DECstations (debian-mipsel — little-endian).
     - `released <https://www.debian.org/releases/stable/mips/release-notes/>`_

   * - :doc:`mipsel <mips>`
     - MIPS (little-endian mode)
     - First officially released with Debian 3.0. Debian is being ported to
       the MIPS architecture which is used in SGI machines (debian-mips —
       big-endian) and Digital DECstations (debian-mipsel — little-endian).
     - `released <https://www.debian.org/releases/stable/mipsel/release-notes/>`_

   * - powerpc
     - Motorola/IBM PowerPC
     - First officially released with Debian 2.2. This port runs on many of
       the Apple Macintosh PowerMac models, and on the CHRP and PReP open
       architecture machines.
     - `released <https://www.debian.org/releases/stable/powerpc/release-notes/>`_

   * - ppc64el
     - POWER7+, POWER8
     - First officially released with Debian 8.0. Little-endian port of ppc64,
       using the new Open Power ELFv2 ABI.
     - `released <https://www.debian.org/releases/stable/ppc64el/release-notes/>`_

   * - s390x
     - System z
     - First officially released with Debian 7.0. A 64-bit userland for IBM System z mainframes.
     - `released <https://www.debian.org/releases/stable/s390x/release-notes/>`_


List of in-progress ports
-------------------------------------------------------------------------

.. list-table:: in-progress ports
   :widths: 10 10 70 10
   :header-rows: 1

   * - Port
     - Architecture
     - Description
     - Status

   * - :doc:`hurd-i386 <hurd>`
     - 32-bit PC (i386)
     - The GNU Hurd is a new operating system being put together by
       the GNU group. Debian GNU/Hurd is going to
       be one (possibly the first) GNU OS. The current project is
       founded on the i386 architecture.
     - in progress

   * - :doc:`kfreebsd-amd64 <kfreebsd-gnu>`
     - 64-bit PC (amd64)
     - First officially released with Debian 6.0 as a technology preview and
       the first non-Linux port released by Debian. Port of the Debian GNU
       system to the kernel of FreeBSD. Is no longer part of the official release
       since Debian 8.
     - in progress

   * - :doc:`kfreebsd-i386 <kfreebsd-gnu>`
     - 32-bit PC (i386)
     - First officially released with Debian 6.0 as a technology preview and
       the first non-Linux port released by Debian. Port of the Debian GNU
       system to the kernel of FreeBSD. Is no longer part of the official release
       since Debian 8.
     - in progress

   * - :doc:`m68k <m68k>`
     - Motorola 68k
     - First officially released with Debian 2.0. The port failed to make
       the release criteria for Debian 4.0 and has therefore not been included
       in Etch and later releases and has been moved to debian-ports following that.
       The Debian m68k port runs on a wide variety
       of computers based on the Motorola 68k series of processors — in
       particular, the Sun3 range of workstations, the Apple Macintosh personal
       computers, and the Atari and Amiga personal computers.
     - in progress

   * - `mips64el <https://wiki.debian.org/mips64el>`_
     - MIPS (64-bit little-endian mode)
     - This port is little-endian, uses the N64 ABI, the MIPS64r1 ISA and hardware floating-point.
     - in progress

   * - `powerpcspe <https://wiki.debian.org/PowerPCSPEPort>`_
     - PowerPC Signal Processing Engine
     - A port to the "Signal Processing Engine" hardware present on 
       low-power 32-bit FreeScale and IBM "e500" CPUs.
     - in progress

   * - `sh4 <https://wiki.debian.org/SH4>`_
     - SuperH
     - A port to Hitachi SuperH processors. Also supports the open source
       `J-Core <http://j-core.org/>`_ processor.
     - in progress

   * - `sparc64 <https://wiki.debian.org/Sparc64>`_
     - 64-bit SPARC
     - A 64-bit port to SPARC processors.
     - in progress

   * - `x32 <https://wiki.debian.org/X32Port>`_
     - 64-bit PC with 32-bit pointers
     - X32 is an ABI for amd64/x86_64 CPUs using 32-bit pointers.
       The idea is to combine the larger register set of x86_64 with
       the smaller memory and cache footprint resulting from 32-bit pointers.
     - in progress


List of discontinued ports (historical)
-------------------------------------------------------------------------

.. list-table:: discontinued or suspended ports
   :widths: 10 10 70 10
   :header-rows: 1

   * - Port
     - Architecture
     - Description
     - Status

   * - :doc:`alpha <alpha>`
     - Alpha
     - First officially released with Debian 2.1.
       It failed the criteria for inclusion into the release of Debian 6.0,
       and was in consequence removed from the archive.
     - discontinued

   * - :doc:`arm <arm>`
     - OABI ARM
     - This port runs on a variety of embedded hardware, like routers or NAS
       devices. The arm port was first released with Debian 2.2, and was
       supported up to and including Debian 5.0, where it was replaced with armel.
     - replaced by :ref:`armel`

   * - `AVR32 <http://avr32.debian.net/>`_
     - Atmel 32-bit RISC
     - Port to Atmel's 32-bit RISC architecture, AVR32.
     - dead

   * - :doc:`hppa <hppa>`
     - HP PA-RISC
     - First officially released with Debian 3.0, this is a port 
       to Hewlett-Packard's PA-RISC architecture.
       It failed the criteria for inclusion into the release of Debian 6.0,
       and was in consequence removed from the archive.
     - discontinued

   * - :doc:`ia64 <ia64>`
     - Intel Itanium IA-64
     - First officially released with Debian 3.0. This is a port to Intel's
       first 64-bit architecture. Note: this should not be confused with the
       latest Intel 64-bit extensions for Pentium 4 and Celeron processors,
       called Intel 64; for these, see the AMD64 port. With Debian 8 ia64 was
       removed from the release due to insufficient developer support.
     - discontinued

   * - `m32 <http://www.linux-m32r.org/>`_
     - M32R
     - Port to the 32-bit RISC microprocessor of Renesas Technology.
     - dead

   * - :doc:`netbsd-i386 <netbsd>`
     - 32-bit PC (i386)
     - A port of the Debian operating system, complete with apt,
       dpkg, and GNU userland, to the NetBSD kernel. The port, never released,
       has been abandoned.
     - dead

   * - :doc:`netbsd-alpha <netbsd>`
     - Alpha
     - A port of the Debian operating system, complete with apt,
       dpkg, and GNU userland, to the NetBSD kernel. The port, never released,
       has been abandoned.
     - dead

   * - `or1k <http://or1k.debian.net/>`_
     - OpenRISC 1200
     - A port to the `OpenRISC <http://openrisc.net/>`_ 1200 open source CPU.
     - dead

   * - :doc:`s390 <s390>`
     - S/390 and zSeries
     - First officially released with Debian 3.0. This is a port to IBM
       S/390 servers. Was replaced by s390x with Debian 8.
     - replaced by :ref:`s390x`

   * - :doc:`sparc <sparc>`
     - Sun SPARC
     - First officially released with Debian 2.1. This port runs on the Sun
       UltraSPARC series of workstations, as well as some of their successors
       in the sun4 architectures. Since the release of Debian 8 Sparc was no
       longer a release architecture, due to insufficient developer support.
       However, it is to be replaced by Sparc64 soon.
     - to be replaced by sparc64


.. remove Debian Beowulf

.. warning::
  Many of the above computer and processor
  names are trademarks and registered trademarks of their manufacturers. 
  They are used without permission.
