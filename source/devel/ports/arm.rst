====================================================================
ARM Ports
====================================================================

Debian on arm
====================================================================
On these pages you'll find information about the ongoing effort of 
porting Debian GNU/Linux to various versions of the
`ARM architecture <https://en.wikipedia.org/wiki/ARM_architecture>`_
which are found in all types of system, from embedded
through to large server.

Current Status
====================================================================
Debian fully supports three ports to different flavours of
little-endian ARM hardware:

 * **armel** : The `ARM EABI <https://wiki.debian.org/ArmEabiPort>`_ 
   port targets a range of older 32-bit ARM devices, particularly
   those used in NAS hardware and a variety of plug computers.

 * **armhf** : The newer `ARM hard-float <https://wiki.debian.org/ArmHardFloatPort>`_
   port supports newer, more powerful 32-bit
   devices using version 7 of the ARM architecture specification.

 * **arm64** : The `64-bit ARM <https://wiki.debian.org/Arm64Port>`_
   port supports the latest 64-bit ARM-powered devices. 


Other ports to ARM hardware exist / have existed in and around
Debian - see `the wiki <https://wiki.debian.org/ArmPorts>`_
for more links and an overview.

For a full and up-to-date list of the different hardware supported
by each of the ports, check the respective wiki pages. New ARM devices
are released every week, and it's easier for people to keep
information updated there.


Available Hardware for Debian Developers
====================================================================
Multiple :q:`porterbox` machines are made available to Debian developers
and others for ARM porting work:

 * abel.debian.org (armel/armhf)
 * asachi.debian.org (armhf/arm64) 
 * harris.debian.org (armhf)

The machines have development chroot environments which you can
access with *schroot*.  Please see the
`machine database <https://db.debian.org/machines.cgi>`_ for
more information about these machines and
`how to get guest access to porter machines <https://dsa.debian.org/doc/guest-account/>`_ .


Contacts
====================================================================

 * See the `Debian ARM port mailing list <https://lists.debian.org/debian-arm/>`_ .
   It's also a good idea to sign up with the `linux-arm <http://www.arm.linux.org.uk/mailinglists/>`_
   mailing list.

 * IRC: the `#debian-arm channel on irc.debian.org <irc://irc.debian.org/debian-arm>`_.


People
----------------------------------------------------
This is a list of significant people who are currently involved
in the Debian ARM ports.

 * `Ian Campbell <jc@debian.org>`_ : debian-installer, kernel
 * `Aurelien Jarno <aurel32@debian.org>`_ : ARM buildd maintainer and general porter
 * `Steve McIntyre <steve@einval.com>`_ : Local admin for ARM machines, documentation and general porter
 * `Martin Michlmayr <tbm@cyrius.com>`_ : Documentation, debian-installer
 * `Riku Voipio <riku.voipio@iki.fi>`_ : armel porter and buildd maintainer
 * `Wookey <wookey@wookware.org>`_ : Documentation


Dedication
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Chris Rutter : who was the Project Coordinator and Autobuilder Coordinator
for Debian ARM port got killed in a car accident. We dedicate the ARM port's
release in the Debian GNU/Linux :q:`woody` distribution to his
memory.

Thanks
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
These people were helpful in making the ARM port viable for Debian: Jim Studt,
Jim Pick, Scott Bambrough, Peter Naulls, Tor Slettnes,
Phil Blundell, Vincent Sanders


Links
====================================================================

Debian stuff

 * <a href="http://auric.debian.org/~pb/shame/arm-stats.html">ARM Buildd
Statistics</a>
 * <a href="http://auric.debian.org/~pb/shame/arm.html">ARM Buildd Package Status Information (short)</a>
 *<a href="http://auric.debian.org/~pb/shame/arm-full.html">ARM Buildd Package Status Information (full)</a>


Resources
  <li><a href="http://www.netwinder.org/">NetWinder.org</a> - Linux for NetWinders</li>
  <li><a href="http://www.arm.linux.org.uk/">Russell King's ARM Linux site</a></li>
  <li><a href="http://www.netbsd.org/Ports/arm32/index.html">NetBSD/arm32</a></li>

Docs</strong>

 * <a href="http://www.arm.com/">ARM Ltd.</a> (for documentation)</li>
 * <a href="http://developer.intel.com/design/pca/applicationsprocessors/index.htm">Intel StrongARM/XScale</a> (more documentation)</li>


<p><strong>Projects/Info</strong>
 * <a href="http://www.emdebian.org/">Emdebian</a> - project to shrink Debian to fit embedded systems</li>
 * <a href="http://www.handhelds.org/">www.handhelds.org</a> - good resources on all aspects of handheld Linux</li>


<p><strong>Device Support</strong>
<ul>
 * <a href="http://linux-7110.sourceforge.net/">Psion Series 5 (and Geofox 1)</a></li>
 * <a href="http://www.handhelds.org/Compaq/iPAQH3600/">Compaq iPAQ H3600</a></li>
 * <a href="http://sourceforge.net/projects/linux-7110/">Psion 5mx, 5mxPro and Series 7</a></li>
 * <a href="http://www.lart.tudelft.nl/">LART project</a> - open hardware (StrongARM 1100) design for embedded computing<br></li>
 * <a href="http://www.cse.unsw.edu.au/~pleb/">PLEB project</a> - SA1100-based open hardware for embedded system
 * <a href="http://www.research.digital.com/wrl/itsy/">The Itsy development board</a><br></li>
 * <a href="http://crl.research.compaq.com/projects/personalserver/personal-server-spec.html">Compaq Personal Server</a></li>
</ul>

<p><strong>Manufacturers</strong>
<ul>
 * <a href="http://www.castle.org.uk/">Castle</a> (RiscPC)</li> 
 * <a href="http://www.psion.com/">Psion</a> (ARM-based PDAs)</li>
 * <a href="http://www.compaq.com/">Compaq</a> (ARM-based PDAs, dev boards)</li>
 * <a href="http://www.simtec.co.uk/">Simtec</a> (ARM-based dev boards)</li>
</ul>
