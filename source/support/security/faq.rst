====================================================================
Debian security FAQ
====================================================================

.. contents:: :depth: 2

I received a DSA via debian-security-announce, how can I upgrade the vulnerable packages?
==========================================================================================

As the DSA mail says, you should upgrade the packages affected by the 
announced vulnerability. You can do this by just upgrading (after
updating the list of available packages with ``apt-get update``)
every package in your system with ``apt-get upgrade`` or by
upgrading just a particular package, with ``apt install <package>``.

The announcement mail mentions the source package in which the vulnerability
was present. Therefore, you should update all the binary packages from
that source package. To check the binary packages to update, visit
<tt>https://packages.debian.org/src:<i>source-package-name</i></tt> and
click on <i>[show binary packages]</i> for the distribution you
are updating.

It may also be necessary to restart a service or a running process.
For that, the `checkrestart <https://manpages.debian.org/checkrestart>`_ command 
in `debian-goodies <https://packages.debian.org/debian-goodies>`_ package
might help to find which ones.


The signature on your advisories does not verify correctly!
==========================================================================================

This is most likely a problem on your end.

The `debian-security-announce <https://lists.debian.org/debian-security-announce>`_
list has a filter that only allows messages with a correct signature
from one of the security team members to be posted.

Most likely some piece of mail software on your end slightly changes
the message that breaks the signature. Make sure your software does
not do any MIME encoding or decoding, or tab/space conversions.

.. Known culprits are fetchmail (with the mimedecode option enabled),
   formail (from procmail 3.14 only) and evolution.


What is a CVE identifier?
==========================================================================================

The Common Vulnerabilities and Exposures project assignes
unique names, called CVE identifiers, to specific security
vulnerabilities, to make it easier to uniquely refer to a specific
issue. Debian Security Advisory has :doc:`CVE compatibility <cve-compatibility>`.

More information can be found at `Wikipedia <http://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures>`_.


Does Debian issue a DSA for every CVE id?
==========================================================================================

The Debian security team keeps track of every issued CVE identifier,
connect it to the relevant Debian package and assess its impact in a
Debian context - the fact that something is assigned a CVE id does not
necessarily imply that the issue is a serious threat to a Debian system.
This information is tracked in the
`Debian Security Tracker <https://security-tracker.debian.org>`_
and for the issues that are considered serious a Debian Security Advisory
will be issued.

Low-impact issues not qualifying for a DSA can be fixed in the next
release of Debian, in a point release of the current stable or oldstable
distributions, or are included in a DSA when that is being issued for a
more serious vulnerability.


Can Debian assign CVE identifiers?
==========================================================================================

Debian is a CVE Numbering Authority and can assign ids, but per
CVE policy only to yet-undisclosed issues. If you have an undisclosed
security vulnerability for software in Debian and would like to get an
identifier for it, contact the Debian Security Team. For cases where the
vulnerability is already public, we advise to follow the procedure
detailed in the `CVE OpenSource Request HOWTO <https://github.com/RedHatProductSecurity/CVE-HOWTO>`_.


I've seen DSA 100 and DSA 102, now where is DSA 101?
==========================================================================================

Several vendors (mostly of GNU/Linux, but also of BSD
derivatives) coordinate security advisories for some incidents and
agree to a particular timeline so that all vendors are able to
release an advisory at the same time.  This was decided in order to
not discriminate some vendors that need more time (e.g. when the
vendor has to pass packages through lengthy QA tests or has to
support several architectures or binary distributions).  Our own
security team also prepares advisories in advance.  Every now and
then, other security issues have to be dealt with before the parked
advisory could be released, and hence temporarily leaving out one or
more advisories by number.


I tried to download a package listed in one of the security advisories, but I got a "file not found" error.
==============================================================================================================

Whenever a newer bugfix supersedes an older package on
security.debian.org, chances are high that the old package will be
removed by the time the new one gets installed.  Hence, you'll get
this "file not found" error.  We don't want to distribute packages
with known security bugs longer than absolutely necessary.

Please use the packages from the latest security advisories, which are
distributed through the `debian-security-announce <https://lists.debian.org/debian-security-announce/>`_
mailing list. It's best to simply run ``apt update`` before upgrading the package.


What to do if a random package breaks after a security update?
==========================================================================================

First of all, you should figure out why the package breaks and
how it is connected to the security update, then contact the
security team if it is serious or the stable release manager if it
is less serious.  We're talking about random packages that break
after a security update of a different package.  If you can't
figure out what's going wrong but have a correction, talk to the
security team as well.  You may be redirected to the stable release
manager though.

.. really? debian-security mailing list and filing bug against it's package

How long will security updates be provided?
==========================================================================================

The security team tries to support a stable distribution for
about one year after the next stable distribution has been
released, except when another stable distribution is released
within this year.  It is not possible to support three
distributions; supporting two simultaneously is already difficult
enough.


How is security handled in Debian?
==========================================================================================

Once the security team receives a notification of an incident,
one or more members review it and consider its impact on the stable
release of Debian (i.e. if it's vulnerable or not).
If our system is vulnerable, we work on a fix for the
problem.  The package maintainer is contacted as well, if they didn't
contact the security team already.  Finally, the fix is tested and
new packages are prepared, which are then compiled on all stable
architectures and uploaded afterwards.  After all of that is done,
an advisory is published.


Why are you fiddling with an old version of that package?
==========================================================================================

The most important guideline when making a new package that fixes a
security problem is to make as few changes as possible.  Our users and
developers are relying on the exact behaviour of a release once it is made,
so any change we make can possibly break someone's system.  This is
especially true in case of libraries: make sure you never change the
Application Program Interface (API) or Application Binary Interface (ABI),
no matter how small the change is.

This means that moving to a new upstream version is not a good solution,
instead the relevant changes should be backported.  Generally upstream
maintainers are willing to help if needed, if not the Debian security team
might be able to help.

In some cases it is not possible to backport a security fix, for example
when large amounts of source code need to be modified or rewritten.  If that
happens it might be necessary to move to a new upstream version, but this
has to be coordinated with the security team beforehand.


What is the policy for a fixed package to appear in security.debian.org?
==========================================================================================

Security breakage in the stable distribution warrants a package
on security.debian.org.  Anything else does not.  The size of a
breakage is not the real problem here.  Usually the security team
will prepare packages together with the package maintainer.
Provided someone (trusted) tracks the problem and gets all the
needed packages compiled and submit them to the security team, even
very trivial security problem fixes will make it to
security.debian.org.  Please see below.

Security updates serve one purpose: to supply a fix for a security
vulnerability.  They are not a method for sneaking additional
changes into the stable release without going through normal point
release procedure.


The version number for a package indicates that I am still running a vulnerable version!
==========================================================================================

Instead of upgrading to a new release we backport security fixes to
the version that was shipped in the stable release. The reason we do
this is to make sure that a release changes as little as possible
so things will not change or break unexpectedly as a result of a
security fix. You can check if you are running a secure version of
a package by looking at the package changelog, or comparing its
exact version number with the version indicated in the Debian 
Security Advisory.


I received an advisory, but the build for one processor architecture seems to be missing.
==========================================================================================

Generally the Security Team releases an advisory with builds of the updated
packages for all architectures that Debian supports. However, some architectures
are slower than others and it may happen that builds for most architectures
are ready while some are still missing. These smaller archs represent a small
fraction of our user base. Depending on the urgency of the issue
we may decide to release the advisory forthwith. The missing builds will be
installed as soon as they come available, but no further notice of this will
be given. Of course we will never release an advisory where the i386 or amd64
builds are not present.

.. _how-is-security-handled-for-unstable:

How is security handled for `unstable`?
==========================================================================================

Security for unstable is primarily handled by package maintainers, not
by the Debian Security Team. Although the security team may upload
high-urgency security-only fixes when maintainers are noticed to be
inactive, support for stable will always have priority.

If you want to have a secure (and stable) server you are strongly encouraged
to stay with stable.

.. _how-is-security-handled-for-testing:

How is security handled for `testing`?
==========================================================================================

Security for testing benefits from the security efforts of the entire
project for unstable. However, there is a **minimum two-day migration delay**,
and **sometimes security fixes can be held up by transitions**. The Security
Team helps to move along those transitions holding back important
security uploads, but this is not always possible and delays may occur.
Especially in the months after a new stable release, when many new versions
are uploaded to unstable, security fixes for testing may lag behind.

If you want to have a secure (and stable) server you are strongly
encouraged to stay with stable.


How is security handled for `contrib` and `non-free`?
==========================================================================================

The short answer is: **it's not**.

Contrib and non-free aren't official
parts of the Debian Distribution and are not released, and thus not
supported by the security team.

Some non-free packages are distributed without source or without
a license allowing the distribution of modified versions.
In those cases no security fixes can be made at all.  If it
is possible to fix the problem, and the package maintainer or someone else
provides correct updated packages, then the security team will generally
process them and release an advisory.


The advisory says unstable is fixed in version 1.2.3-1, but unstable has 1.2.5-1, what's up?
=============================================================================================

We try to list the first version in unstable that fixed the problem.
Sometimes the maintainer has uploaded even newer versions in the meantime.
Compare the version in unstable with the version we indicate. If it's the
same or higher, you should be safe from this vulnerability. If you want to
be sure, you can check the package changelog with ``apt changelog <package name>``
and search for the entry announcing the fix.


Why are there no official mirrors for security.debian.org?
==========================================================================================

Actually, there are. There are several official mirrors, implemented
through DNS aliases. The purpose of security.debian.org is to make security
updates available as quickly and easily as possible.

Encouraging the use of unofficial mirrors would add extra complexity
that is usually not needed and that can cause frustration if these
mirrors are not kept up to date.


.. _security-contact:

How can I reach the security team?
==========================================================================================

Security information can be sent to security@debian.org or 
team@security.debian.org, both of which are read by the members of
the security team. **If desired, email can be encrypted with the GPG**.

.. note::

  Debian Security Team GPG key ID:
  `0x0D59D2B15144766A14D241C66BAF400B05C3E651 <https://pgp.mit.edu/pks/lookup?search=0x0D59D2B15144766A14D241C66BAF400B05C3E651>`_.

  For the PGP/GPG keys of :ref:`individual security team members <security team>`,
  please refer to the `keyring.debian.org <http://keyring.debian.org>`_ keyserver.


I guess I found a security problem, what should I do?
==========================================================================================

* Vulnerability is **already publicly known**

  Be sure to file a bug report in the `Debian BTS <https://bugs.debian.org>`_, and tag it "security".

* Vulnerability is **not yet public**

  Please always contact the security team. 
  If the Debian security team confirms the vulnerability and other vendors are
  likely to be vulnerable as well, they usually contact other vendors as
  well. They will try to coordinate security advisories with the other vendors,
  so all major distributions are in sync.

If you are a Debian maintainer, see also :doc:`faq-for-maintainer`.


How can I help with security?
==========================================================================================

Please review each problem before reporting it to the security team.
If you are able to provide patches, that would speed up the process.

.. bugtraq? it's outdated... so it should be removed or modified

.. Do not simply forward bugtraq mails,
   because we already receive them &mdash; but do provide us with
   additional information about things reported on bugtraq.

A good way to get started with security work is helping
out on the `Debian Security Tracker instructions <https://security-tracker.debian.org/tracker/data/report>`_.


How is the security team composed?
==========================================================================================

The Debian security team consists of
:ref:`several officers and secretaries <organization-security">`.
The security team itself appoints people to join the team.

