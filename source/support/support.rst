============================================================================
Support
============================================================================

* :doc:`Documentation </doc/index>`

  Before searching for support from someone else, it's usually good to try
  to find an answer to your problem yourself. That way you will usually get
  the answers you need, and even if you don't, the experience of reading the
  documentation will likely be useful for you in the future.

  There is a fair amount of documentation available in Debian &mdash; please
  refer to the :doc:`Debian documentation </doc/>`  web page.


* `Known problems <https://www.debian.org/releases/stable/>`_

  Limitations and severe problems of the current stable distribution
  (if any) are described on `the release pages <https://www.debian.org/releases/stable/>`_.

  Pay particular attention to the `release notes <https://www.debian.org/releases/stable/releasenotes>`_
  and the `errata <https://www.debian.org/releases/stable/errata>`_.


* `Wiki <https://wiki.debian.org/>`_

  Solutions to common problems, howto's, guides, tips and other documentation
  can be found at the <a href="https://wiki.debian.org/">Debian Wiki</a>.  Like
  all wikis, this wiki is constantly changing and we welcome your edits.


* :doc:`Mailing lists <MailingLists/index>`

  Debian is developed through distributed development all around
  the world. Therefore e-mail is a preferred way to discuss various items.
  Much of the conversation between Debian developers and users is managed
  through several mailing lists.

  There are several publicly available mailing lists. For more information,
  see <a href="MailingLists/">Debian mailing lists</a> page.


.. Note to translators:
   You might want to adapt the following paragraph, stating which list
   is available for user support in your language instead of English.

  For user support in English, please contact the 
  <a href="https://lists.debian.org/debian-user/">debian-user mailing list</a>.

  For user support in other languages, please check the
  <a href="https://lists.debian.org/users.html">mailing
  lists index for users</a>.

  There are of course many other mailing lists, dedicated to some aspect
  of the vast Linux ecosystem, which are not Debian-specific. Use your
  favorite search engine to find the most suitable list for your purpose.

.. remove newsgroups


<toc-add-entry name="web">Web sites</toc-add-entry>

<h3>Forums</h3>

# Note to translators:
# If there is a specific Debian forum for your language you might want to
# insert here a paragraph stating which list is available for user support
# in your language and pointing to the English forums.
# <a href="http://someforum.example.org/">someforum</a> is a web portal
# on which you can use your language to discuss Debian-related topics,
# submit questions about Debian, and have them answered by other users.
#
# <a href="http://www.debianhelp.org/">debianHELP</a> and <a
# href="http://forums.debian.net">Debian User Forums</a> are web portals
# on which you can use the English language to discuss Debian-related topics,
# submit questions about Debian, and have them answered by other users.

<a href="http://www.debianhelp.org/">debianHELP</a> and <a
href="http://forums.debian.net">Debian User Forums</a> are web portals on which
you can discuss Debian-related topics, submit questions about Debian, and have
them answered by other users.

<h3>Question &amp; Answer</h3>

<a href="http://ask.debian.net">ask.debian.net</a> is a web-based Question
and Answer support system on which you can submit questions and have them
answered by other members. A vote-based reputation system is also provided,
enabling ranking of user-provided content.

<h3>Other web resources</h3>

<a
href="http://www.debian-administration.org/">Debian-Administration.org</a>
provides tips and resources for Debian system administrators.

Helpful links about Unix:

<ul>
  <li><a href="http://www.dmoz.org/Computers/Software/Operating_Systems/Unix/">\
      Open Directory &mdash; Unix</a></li>
  <li><a href="http://unixhelp.ed.ac.uk/">UNIXhelp for users</a></li>
  <li><a href="http://personal.stevens.edu/~khockenb/comp-unix-admin.html">\
      comp.unix.admin FAQ</a></li>
</ul>


<toc-add-entry name="maintainers">Reaching Package Maintainers</toc-add-entry>

There are two ways of reaching package maintainers. If you need to
contact the maintainer because of a bug, simply file a bug report (see the
Bug Tracking System section below). The maintainer will get a copy of the
bug report.

If you simply want to communicate with the maintainer, then you can use
the special mail aliases set up for each package. Any mail sent to
&lt;<em>package name</em>&gt;@packages.debian.org will be forwarded to the
maintainer responsible for that package.


<toc-add-entry name="bts" href="Bugs/">The Bug Tracking System</toc-add-entry>

The Debian distribution has a bug tracking system which
details bugs reported by users and developers.  Each bug is given a
number, and is kept on file until it is marked as having been dealt
with.

To report a bug, you can use one of the bug pages listed below, or you
can use the Debian package <q>reportbug</q> to automatically file a bug report.

Information on submitting bugs, viewing the currently active bugs, and
the bug tracking system in general can be found at the
<a href="Bugs/">bug tracking system web pages</a>.


<toc-add-entry name="consultants" href="consultants/">Consultants</toc-add-entry>

Debian is free software and offers free help through mailing lists. Some
people either don't have the time or have specialized needs and are willing
to hire someone to maintain or add additional functionality to their Debian
system.  See the <a href="consultants/">consultants page</a> for a list
of people/companies.


<toc-add-entry name="irc">On-line Real Time Help Using IRC</toc-add-entry>

<a href="http://www.irchelp.org/">IRC (Internet Relay Chat)</a> is a way
to chat with people from all over the world in real time.
IRC channels dedicated to Debian can be found on
<a href="https://www.oftc.net/">OFTC</a>.

To connect, you need an IRC client. Some of the most popular clients are
<a href="https://packages.debian.org/stable/net/xchat">XChat</a>,
<a href="https://packages.debian.org/stable/net/ircii">ircII</a>,
<a href="https://packages.debian.org/stable/net/irssi">irssi</a>,
<a href="https://packages.debian.org/stable/net/epic5">epic5</a> and
<a href="https://packages.debian.org/stable/net/kvirc">KVIrc</a>,
all of which have been packaged for
Debian. OFTC also offers a <a href="https://www.oftc.net/WebChat/">WebChat</a>
web interface which allows you to connect to IRC with a browser without
the need to install any local client.

Once you have the client installed, you need to tell it to connect
to the server. In most clients, you can do that by typing::

  /server irc.debian.org


.. Note to translators:
   You might want to insert here a paragraph stating which IRC channel is available 
   for user support in your language and pointing to the English IRC channel.
   Once you are connected, join channel <code>#debian-foo</code> by typing
   <pre>/join #debian</pre>
   for support in your language.
   For support in English, read on

Once you are connected, join channel <code>#debian</code> by typing::

  /join #debian

.. note:: 
 
 Clients like XChat often have a different, graphical user interface
 for joining servers/channels.

At this point you will find yourself among the friendly crowd of
<code>#debian</code> inhabitants. You're welcome to ask questions about
Debian there. You can find the channel's faq at 
<url "https://wiki.debian.org/DebianIRC" />.


There's a number of other IRC networks where you can chat about Debian,
too. One of the more prominent ones is the
<a href="http://freenode.net/">freenode IRC network</a> at
<kbd>chat.freenode.net</kbd>.


<toc-add-entry name="other">Other support resources</toc-add-entry>

Check the <a href="misc/related_links">related links</a>.
