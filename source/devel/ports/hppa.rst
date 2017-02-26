PA-RISC Port

Status
==============================================================
HPPA became an officially supported Debian architecture in release 
3.0 (woody), and was dropped as of stable release 6.0 (squeeze).

Additional information about the port may be found at
<a href="http://parisc-linux.org/">http://parisc-linux.org/</a>.


Contacts
==============================================================
The principal instigator of this port was Bdale Garbee, but he no longer
actively contributes to it.  

The best way to ask questions now is via the mailing list.

<h2>Mailing List</h2>

<p>
To subscribe to the mailing list for this port, send a message with the
word "subscribe" as the subject to
<a
href="mailto:debian-hppa-request@lists.debian.org">\
debian-hppa-request@lists.debian.org</a> to sign up, or use the 
<a href="$(HOME)/MailingLists/subscribe">mailing list subscription</a> page.
<p>
The list is archived at the
<a href="https://lists.debian.org/debian-hppa/">list archives</a>.

Links
==============================================================
<ul>

<li><a href="http://parisc-linux.org/">The PA-RISC Linux Project Web</a>
<li><a href="http://www.pateam.org/parisc-linux-boot/doc.html">ESIEE's HOWTO Documents</a>
<li><a href="http://docs.hp.com/hpux/hw/">HP Systems Documentation</a>
<li><a href="http://h21007.www2.hp.com/dev/">\
	HP PA-RISC Architecture Reference Documents, Etc</a>
<li><a href="http://www.openpa.net/">The OpenPA Project</a>

</ul>

#use wml::debian::template title="PA-RISC Port -- Systems" NOHEADER="yes"
#include "$(ENGLISHDIR)/ports/hppa/menu.inc"

<h2>Systems Overview</h2>
==============================================================
<h3>HP9000 715/50 (Scorpio)</h3>

Linux will work quite well on that machine, but you may have to run
with a serial console, as Linux doesn't support graphics on all
hardware yet.  Also, Linux doesn't support EISA cards on any PA-RISC
boxes yet, so if you have any of those they won't work.
#use wml::debian::template title="PA-RISC Port -- News" NOHEADER="yes"
#include "$(ENGLISHDIR)/ports/hppa/menu.inc"

Old News about Debian for PA-RISC

<h3><:=spokendate ("2001-08-06"):></h3>

<p><strong>Debian accepts hppa for release with Debian 3.0 (woody)!</strong>

<p>
It is with great pleasure that we announce the acceptance of hppa as an 
architecture for the upcoming Debian 3.0 stable release, codename woody.
Installation tools for hppa are now in the woody tree, and packages now in
unstable are beginning to be promoted to the testing/woody tree.

<h3><:=spokendate ("2001-07-17"):></h3>

<p><strong>Official Request to Release with Debian 3.0 (woody)</strong>

<p>
Nearly 70% of all Debian packages are built and up to date in the archive,
an automated build system is running smoothly, installation tools are 
available in the archive, and the number of running systems is growing
steadily.

<h3><:=spokendate ("2001-05-31"):></h3>

<p><strong>HP Releases 0.9 CD Images!</strong>

<p>
HP has made a snapshot of the "sid" unstable Debian tree for hppa available
as a set of CDROM images.  See <a href="http://parisc-linux.org/release-0.9/">
the release page </a> for more information.  This release makes it plausible
that the hppa architecture might be ready to release with woody, though there
is much work left to do between now and then!

<h3><:=spokendate ("2000-10-16"):></h3>

<p><strong>Binary Trees Created</strong>

<p>
Binary trees for the hppa architecture were added to the 'sid' distribution
on Debian's master site today.  Bdale is running an auto-builder, and packages
should start showing up on Debian mirror sites shortly.  Installation info and
some critical packages are still available only through the 
<a href="http://parisc-linux.org/">PA-RISC Linux</a> 
web site, however.

<h3><:=spokendate ("2000-08-01"):></h3>

<p><strong>Name Change</strong>

<p>
At OLS, the issue of using 'parisc' vs 'hppa' for the Debian architecture
string was finally decided, in favor of 'hppa'.  This ports page is being
moved to reflect the change, and a request is in the works to rename the 
debian-parisc mailing list to debian-hppa.  

<h3><:=spokendate ("2000-03-31"):></h3>

<p><strong>HP Contributes Build Machine</strong>

<p>
HP has made a 
J5000
available to Debian on long-term loan to aid in compiling packages when we get
to that point.
<p>
Also, the mailing list debian-parisc has been activated.

<h3><:=spokendate ("2000-03-04"):></h3>

<p><strong>Debian PA-RISC Port Officially Starts</strong>

<p>
A new mailing list, debian-parisc, has been requested but is not active yet.
