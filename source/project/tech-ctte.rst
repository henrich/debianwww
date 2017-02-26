==========================================================================
Debian Technical Committee
==========================================================================
The Technical Committee is established by the
:doc:`constitution`, section 6.  It is the body
which makes the final decision on technical disputes in the Debian project.

How to refer a question to the committee
==========================================================================

#. Before referring a decision to the Technical Committee, you should try
   to resolve it yourself.  Engage in a constructive discussion and try
   to understand the other person's point of view.  If, after discussion,
   you've identified a technical question which you can't agree on, you
   can put it to the committee:

#. Write up a summary of the disagreement, preferably agreeing it with
   your opponent, and send it to the bug tracking system
   *as a new bug*, against the pseudo-package ``tech-ctte``.
   In your summary mention any relevant existing bug numbers and mailing
   list archive urls.

#. Send an email to all relevant parties inviting them to subscribe to the
   bug.  If there are existing bug(s) open about the
   issue, set the new tech-ctte bug to block them (but if you don't know
   how to do this, don't worry - we will do it for you.)

#. The committee will discuss your question in the tech-ctte bug.
   We will generally not CC discussion to individual participants,
   unless we invite them into the conversation to ask them a specific
   question.  Everyone who is interested in the issue should subscribe
   to the bug using the BTS.

#. The committee will aim to make a decision as soon as possible.  In
   practice this process is likely to take many weeks, or perhaps
   longer.  If the question is particularly urgent please say so.

#. Sometimes, one side or other is convinced, during the committee's
   deliberations, by the merit of the other side's arguments.  This is a
   good thing!  If it happens, the committee need not make a formal
   decision, and the bug report can be closed, or reassigned, as appropriate.


Some caveats about contacting the committee
==========================================================================

* A sound and vigorous debate is important to ensure that all the
  aspects of an issue are fully explored.  When discussing technical
  questions with other developers you should be ready to be challenged.
  You should also be prepared to be convinced!  There is no shame in
  seeing the merit of good arguments.

* Please conduct your technical discussions with other maintainers
  in a calm and civilised way; do not use insults, or question their
  competence.  Instead, address yourself to your opponents' arguments.

* The committee is only empowered to make technical decisions.  If
  you feel that someone has been misbehaving, the committee probably
  can't help you much.  You may wish to talk to the `Project Leader <leader@debian.org>`_.

* The bug traffic will also appear on the committee mailing list,
  `debian-ctte@lists.debian.org <https://lists.debian.org/debian-ctte/>`_.
  Anyone else who wishes to do so may subscribe to
  the debian-ctte mailing list and see our deliberations.  But please
  do not send messages relating to specific issues directly to the
  list.

.. warning::

 To post to the committee mailing list you must either be
 subscribed to the list from your posting address, or PGP-sign your
 message.  This is an anti-spam measure.  We apologise for the
 inconvenience, but this setup makes it possible for committee
 members to pay proper attention to the committee list mails.


Membership
==========================================================================

The current membership of the committee is documented on the
:ref:`Debian Organizational Structure <organization>` page.


Archives, status and VCS repository
==========================================================================

 * The committee mailing list is `archived <https://lists.debian.org/debian-ctte/>`_.
 * Questions pending decision can be reviewed in the
   `bug tracking system <https://bugs.debian.org/cgi-bin/pkgreport.cgi?pkg=tech-ctte>`_.
 * The TC sometimes uses its `shared git repository <https://anonscm.debian.org/cgit/collab-maint/debian-ctte.git>`_
   for collaboration.


Formal technical decisions, including recommendations and advice
==========================================================================

The decision history sections are not necessarily up to date.
(`Older questions and decisions <https://bugs.debian.org/cgi-bin/pkgreport.cgi?pkg=tech-ctte;archive=yes>`_
can be viewed in the bug tracking system.)

 * 2015-09-04
     `Bug #741573 <https://bugs.debian.org/741573>`_: The
     technical committee adopts the changes to policy regarding menu
     entries proposed by Charles Plessy, and additionally resolves that
     packages providing desktop files shall not also provide a menu
     file.

 + 2015-06-19
     `Bug #750135 <https://bugs.debian.org/750135>`_: The
     technical committee encourages Christian Perrier to implement his
     proposal for maintenance of the Aptitude project.

 * 2014-11-15
     `Bug #746578 <https://bugs.debian.org/746578>`_: The
     committee decided that systemd-shim should be the first listed
     alternative dependency of libpam-systemd instead of systemd-sysv.

 * 2014-08-01
     `Bug #746715 <https://bugs.debian.org/746715>`_: The
     technical committee expects maintainers to continue to support the
     multiple available init systems.

 * 2014-08-01
     `Bug #717076 <https://bugs.debian.org/717076>`_: The
     committee decided that the default libjpeg implementation should be
     libjpeg-turbo.

 * 2014-02-11
     `Bug #727708 <https://bugs.debian.org/727708>`_: The
     committee decided that the default init system for Linux architectures
     in jessie should be systemd.

 * 2013-03-06
     `Bug #698556 <https://bugs.debian.org/698556>`_: The
     committee overrules the maintainer of isdnutils to require the
     inclusion of code to create isdn devices by isdnutils.

 * 2012-12-21
     `Bug #688772 <https://bugs.debian.org/688772>`_:
     The committee overrules the dependency of meta-gnome
     on network-manager while concerns raised in
     `§4 of the decision in #681834 <href="https://bugs.debian.org/681834#273>`_
     remain unaddressed.

 * 2012-10-05
     `Bug #573745 <https://bugs.debian.org/573745>`_:
     The committee declines to change the maintainer
     of python packages in Debian.

 * 2012-09-14
     `Bug #681834 <https://bugs.debian.org/681834>`_: gnome-core
     should Recommends: network-manager; override maintainer.

 * 2012-08-24
     `Bug #681783 <https://bugs.debian.org/681783>`_: Policy on
     Recommends is correct; Recommends is fine in metapackages.

 * 2012-08-14
     `Bug #681687 <https://bugs.debian.org/681687>`_:
     evince's lack of mime type entry for PDF is RC bug
     (decline to overrule release team).
 * 2012-07-12
     `Bug #614907 <https://bugs.debian.org/614907>`_:
     nodejs must use /usr/bin/nodejs, node must change
     to ax25-node and provide /usr/sbin/ax25-node, and
     transition packages and legacy packages defined.

 * 2012-04-05
     `Bug #640874 <https://bugs.debian.org/640874>`_: decline to
     override policy maintainers. debian/rules must be a Makefile.

 * 2012-03-21
     `Bug #629385 <https://bugs.debian.org/629385>`_:
     dpkg-buildpackage will implement build-arch testing using make -qn.

 * 2012-02-27
     `Bug #607368 <https://bugs.debian.org/607368>`_: decline to
     override the kernel maintainer team's ABI numbering policy.

 * 2012-02-05
    `Bug #658341 <https://bugs.debian.org/658341>`_: multi-arch
    enabled dpkg may be uploaded to experimental and unstable by Raphaël
    Hertzog without waiting for primary maintainer code review.

 * 2010-12-01
    `Bug #587886 <https://bugs.debian.org/587886>`_:
    lilo should remain in unstable. Matt Arnold and Joachim
    Wiedorn are to be joint maintainers of lilo.

 * 2009-09-04
    `Bug #535645 <https://bugs.debian.org/535645>`_:
    decline to override ftp team's removal of ia32-libs-tools;
    reaffirm ftp team's ability to remove packages;
    recommend clarification of reasons for removal,
    and mechanism of reintroduction to the archive.

 * 2009-08-27
    `Bug #510415 <https://bugs.debian.org/510415>`_:
    allow Qmail into Debian after fixing delayed-bounce
    issue with RC bug to block transition for one month

 * 2009-07-30
    `Bug #539158 <https://bugs.debian.org/539158>`_: refuse to
    override udev maintainer; printf suggested to be documented as a
    required builtin in policy.

 * 2009-07-25
    `Bug #484841 <https://bugs.debian.org/484841>`_: by
    default, /usr/local is not writable by group staff; change can be
    implemented after transition plan which enables administrators to
    keep the current behavoir.

 * 2007-12-10
    `Bug #412976 <https://bugs.debian.org/412976>`_:
    keep current behavior and existing policy regarding mixmaster's use of /etc/default.

 * 2007-06-22
    `Bug #367709 <https://bugs.debian.org/367709>`_:
    a libstdc++ udeb should not be created.

 * 2007-06-19
    `Bug #341839 <https://bugs.debian.org/341839>`_:
    the output of ``md5sum`` should not change.

 * 2007-04-09
    `Bug #385665 <https://bugs.debian.org/385665>`_:
    ``fluidsynth remains in main.

 * 2007-04-09
    `Bug #353277 <https://bugs.debian.org/353277>`_,
    `Bug #353278 <https://bugs.debian.org/353278>`_:
    ``ndiswrapper`` remains in main.

 * 2007-03-27
    `Bug #413926 <https://bugs.debian.org/413926>`_:
    ``wordpress`` should be included in etch.

 * 2004-06-24
    `Bug #254598 <https://bugs.debian.org/254598>`_:
    ``amd64`` is a fine name for that architecture.
    `Full text <https://lists.debian.org/debian-ctte/2004/debian-ctte-200406/msg00115.html>`_.
    In favour: Wichert, Raul, Guy, Manoj, Ian. Voting period ended early; no other votes.

 * 2004-06-05
    `Bug #164591 <https://bugs.debian.org/164591>`_,
    `Bug #164889 <https://bugs.debian.org/164889>`_:
    ``md5sum < /dev/null`` should produce the bare md5sum value.
    `Full text <https://lists.debian.org/debian-ctte/2004/debian-ctte-200406/msg00032.html>`_.
    In favour: Guy, Ian, Manoj, Raul. No other votes.

 * 2002-10-06
    `Bug #104101 <https://bugs.debian.org/104101>`_,
    `Bug #123987 <https://bugs.debian.org/123987>`_,
    `Bug #134220 <https://bugs.debian.org/134220>`_,
    `Bug #161931 <https://bugs.debian.org/161931>`_:
    The default kernel should have VESA framebuffer support included.
    `Full text <https://lists.debian.org/debian-ctte/2002/debian-ctte-200211/msg00043.html>`_.
    In favour: Ian, Jason, Raul; against: Manoj. No other votes.

 * 2002-07-19
    `Bug #119517 <https://bugs.debian.org/119517>`_:
    Packages may sometimes contain binaries whose libraries are only
    referred to in Suggests.
    `Full text <https://lists.debian.org/debian-ctte/2002/debian-ctte-200207/msg00017.html>`_.
    In favour: Ian, Wichert; against: Bdale, Manoj; no-one else voted and Ian used his casting vote.


NB that decisions from before the 1st of April 2002 are not yet recorded here.


Formal nontechnical and procedural decisions
==========================================================================

 * 2015-03-05
     Approved Sam Hartman, Tollef Fog Heen and Didier Raboud as
     candidates for the committee. (`Full text <https://lists.debian.org/debian-ctte/2015/03/msg00023.html>`_.
     In favour: Don, Bdale, Andreas, Colin, Steve, Keith.
     Appointment approved by the DPL 2015-03-08;
     `Full text <https://lists.debian.org/debian-devel-announce/2015/03/msg00003.html>`_).

 * 2013-11-07
     Approved Keith Packard as member of the technical committee
     (`resolution <https://lists.debian.org/debian-ctte/2013/11/msg00041.html>`_)

 * 2011-08-24
     Approved Colin Watson as member of the technical committee
     (`for appointment <https://lists.debian.org/debian-devel-announce/2011/08/msg00004.html>`_)

 * 2009-01-11
     Approved Russ Allbery and Don Armstrong as members of the technical committee
     (`summary <https://lists.debian.org/debian-ctte/2009/01/msg00053.html>`_)

 * 2006-04-11
     Elected Bdale as chair
     (`for vote <https://lists.debian.org/debian-ctte/2006/04/msg00042.html>`_)

 * 2006-02-27
     Elected Steve as chair
     (`for summary <https://lists.debian.org/debian-ctte/2006/02/msg00085.html>`_)

 * 2005-12-20
     Approved Steve Langasek, Anthony Towns and Andreas Barth
     as candidates for the committee.
     (`Full text <https://lists.debian.org/debian-ctte/2005/12/msg00042.html>`_.
     In favour: Bdale, Manoj.  Expressions of support,
     with apologies, after end of the voting period: Ian, Raul.
     None against or abstaining;  Appointment approved by the DPL 2006-01-05;
     `Full text <https://lists.debian.org/debian-project/2006/01/msg00013.html>`_).

 * 2005-12-20
     Proposed the removal of Wichert, Guy, and Jason from the committee.
     (`Motion text <https://lists.debian.org/debian-ctte/2005/12/msg00000.html>`_;
     `results <https://lists.debian.org/debian-ctte/2005/12/msg00028.html>`_.
     In favour: Manoj, Raul.  Guy: in favour of his own removal; no opinion otherwise.
     Ian: in favour of removal of Jason; against otherwise.
     Removal approved by the DPL 2006-01-05;
     `Full text <https://lists.debian.org/debian-project/2006/01/msg00013.html>`_.)

 * 2002-07-05
     Passed the question of proper use of bug system
     severities (`Bug #97671 <https://bugs.debian.org/97671>`_)
     on to the BTS admins and project leader.
     (`Full text <https://lists.debian.org/debian-ctte/2002/debian-ctte-200207/msg00002.html>`_.
     In favour: Ian, Jason, Bdale; none against or abstaining.)

 * 2002-01-31
     Appointed Ian Jackson as chairman, following Raul's
     resignation from the post. (In favour: Dale, Ian, Manoj, Raul, Wichert;
     none against or abstaining.)

NB that decisions from before the 31st of January 2002 are not yet
recorded here.


Retired members
==========================================================================

 Thanks to the following people who have served on the committee:

 * Colin Watson (2011-08-24 - 2015-03-05)
 * Ian Jackson (to 2014-11-19)
 * Russ Allbery (2009-01-11 - 2014-11-16)
 * Manoj Srivasta (to 2012-08-12)
 * Anthony Towns (2006-01-04 - 2009-01-05)
 * Raul Miller (to 2007-04-30)
 * Wichert Akkerman (to 2006-01-05)
 * Jason Gunthorpe (to 2006-01-05)
 * Guy Maor (to 2006-01-05)
 * Dale Scheetz (to 2002-09-02)
 * Klee Dienes (to 2001-05-21)

