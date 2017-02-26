=================================================================================
Community Distribution Patent Policy FAQ
=================================================================================

Version: 1.0
Published: 8 July 2011

Introduction
=================================================================================

For whom is this document intended?
---------------------------------------------------------------------------------
This document presents information about patents and patent liability useful
for developers working on community distributions of Free and Open Source
Software (FOSS).  By community distributions, we mean collections of free
software packages maintained and distributed by organizations composed of
volunteers, where neither the organization nor the volunteers seek to make a
profit from the activity.  Such community-based distributions may sell as well
as give away their work product, possibly on CDs or USB storage media or by
paid-for downloads as well as by gratis distribution.

This document has been prepared by lawyers at the
`Software Freedom Law Center <http://www.softwarefreedom.org">`_ (SFLC) 
at the request of the `Debian project <https://www.debian.org/>`_, 
and may be helpful to similar community FOSS
distributions.  Its statements about legal matters are accurate as of the date
of composition regarding US law, and may be applicable to other legal systems.
But this document does not constitute legal advice.  It has not been based on
analysis of any particular factual situation, and any lawyer providing an
opinion on the questions presented below would need to ascertain the particular
facts and circumstances that might vary this information in a particular
setting.  You should not rely upon this document to make decisions affecting
your project's legal rights or responsibilities in a real-life situation
without consulting SFLC or other lawyers.

Background on Patents
=================================================================================

What is a patent?
---------------------------------------------------------------------------------

A patent is a state-granted monopoly granting an inventor exclusive rights to
make, sell, offer for sale, have made, or import the claimed invention for the
limited term of the patent.  The patent holder may then license, on an
exclusive or non-exclusive basis, one or more of the rights granted.


How long is a patent's term?
---------------------------------------------------------------------------------

Generally, patents issued in the last 15 years by most governments expire 20
years from the filing date of the patent application.  US patents with a filing
date before June 8, 1995, provide protection for up to 17 years counting from
the date of grant, or 20 years from the filing date, whichever occurs later.

There are exceptions.  Patents may have their terms extended by the issuing
office or a court, but this rarely happens for patents on software.  Patent
terms may also be shortened by agreement with the applicant during
<q>prosecution</q>, that is, during the patent office procedure leading to issuance.
If a patent's terms has been shortened during prosecution, a <q>terminal
disclaimer</q> statement will appear on the patent's front page.


How does patent protection differ from copyright protection?
---------------------------------------------------------------------------------

A copyright owner has the right to prevent others from making unauthorized
copies of the copyrighted program, but not from independently creating a
program with the same features.  Independent creation is therefore a complete
defense to an allegation of copyright infringement.  In addition, <q>fair use</q> is
a defense against copyright infringement, or is a substantive limitation of
copyright, in every copyright system.  Patent law lacks any fair use exemption,
so independent creation, use for research, or reverse engineering for
interoperation or educational purposes are not defenses against allegations of
patent infringement.


Is there a world-wide patent on anything?
---------------------------------------------------------------------------------

At present, no world-wide patents exist.  Outside the European Union, where
applications may be consolidated, patents generally must be applied for in each
country in which patent protection is sought.


What are patent claims?
---------------------------------------------------------------------------------

Claims, which are the most important part of the patent, determine the actual
scope of the invention to which the patent applies.  Only the claims define
what exclusive rights cover, that is, practicing the claims without license is
infringement.  Reading and understanding the claims of a patent is the key to
determining if a given product or process infringes.

Each claim is a single sentence. Claims begin with a <q>preamble</q> followed by one
or more <q>limitations</q>.

For software to infringe a patent, the software (or system with embedded
software) must implement everything recited in one of the patent's claims. If
you do not practice one or more of the elements of a claim, then you cannot
directly infringe that claim.


What are independent claims?
---------------------------------------------------------------------------------

A patent claim is called <q>independent</q>, if it makes no reference to any other
claim in the patent.


What are dependent claims?
---------------------------------------------------------------------------------

Dependent claims explicitly incorporate the contents of other claims in the
patent. A dependent claim is necessarily narrower in scope than the claim on
which it depends, because it includes one or more additional limitations. In
Venn diagram terms, the area of coverage for a dependent claim is fully
contained within the coverage of the claim it references.


How are software-related patent claims written?
---------------------------------------------------------------------------------

Software-related patent claims in recently-issued patents often take the form
of <q>system</q> or <q>apparatus</q> claims, <q>method</q> claims, and <q>computer program
product</q> or <q>computer-readable medium</q> claims. System claims recite the
elements of a system (which might include one or more computers) as a kind of
machine or static object. Method claims are algorithmic in
form. Computer-readable medium claims typically duplicate the limitations found
in corresponding system or method claims in the patent, but are intended to
cover software embodied in a storage or distribution medium. Computer-readable
medium claims are also often used when claiming inventions that focus on data
structures and user interfaces.

Infringing a patent
=================================================================================

What does <q>patent liability</q> mean?
---------------------------------------------------------------------------------

Liability is a legal responsibility that is enforceable by a court.  In this
document we use term <q>patent liability</q> to encompass orders that a court can
give if a party is found to infringe a patent.  For example, once a party is
found to infringe, a court can order that party to pay money to the patent
holder, called <q>damages</q>, and/or an order to stop the infringing conduct, which
is called an <q>injunction</q>.


What does it mean to <q>infringe</q> a patent?
---------------------------------------------------------------------------------

Infringing a patent means practicing one or more of its claims without license.
If someone uses, makes, sells, has made, offers for sale, or imports software
that practices every element taught by a claim in a patent, that patent is
infringed by the software.

It is possible to be liable for infringement without directly infringing.
<q>Contributing to</q> or <q>inducing</q> infringement also give rise to patent
liability.


What is inducing infringement?
---------------------------------------------------------------------------------

<q>Inducing infringement</q> means actively encouraging someone else to infringe a
patent.  Liability requires proving that the party charged intended to cause a
third party to infringe.  Additionally, the inducer must either know the patent
exists, or strongly suspect its existence and make efforts not to know.  If,
for example, documentation is written by someone with knowledge of a patent's
claims, and that documentation explains how to use the program in an infringing
fashion, the instructions might be held to induce infringement.  Where a
community of volunteers maintains a software package, and associated
documentation, unless the volunteers who produce the documentation know of the
patent supposedly infringed, they cannot induce infringement.


What is contributory infringement?
---------------------------------------------------------------------------------

<q>Contributory infringement</q> means providing material assistance to the
infringement of a patent.  In the context of software, this would mean
providing non-infringing software that could be combined with other software or
hardware to produce an infringing system.  Contributory infringement also
requires knowledge of the patent infringed.  Moreover, if the software has
substantial non-infringing uses, it is not contributory infringement to provide
it, even if it is subsequently used in an infringing combination.


What are the consequences of infringing a patent?
---------------------------------------------------------------------------------

If a party is found to be infringing a patent, courts may order a stop to the
infringing conduct, the payment of damages for past infringement, or both.  In
this document we use term <q>patent liability</q> to encompass all of these
consequences.


What is an injunction?
---------------------------------------------------------------------------------

An injunction is a court order to a person or persons to do something or to
refrain from doing something.  Violating an injunction leads to being held in
contempt of court.  Injunctions may be <q>preliminary</q>, to prevent change of
state while litigation is occurring, or <q>permanent</q>, to order or prohibit
conduct as remedy at the end of a lawsuit, once liability has been found.  A
preliminary injunction to prevent infringing conduct during litigation may be
issued if the court finds damages at the end of the case would be insufficient
to protect the patent holder's rights, and if success in the case is held to be
likely, and the public interest would not be harmed by the injunction.  A
permanent injunction to prevent infringing conduct may result from a finding of
infringement liability.


Can injunctions be issued against FOSS distributions?
---------------------------------------------------------------------------------

Yes.  If a FOSS distribution was found to infringe someone's valid patent, a
permanent injunction against continued distribution of the infringing program
or feature might well occur.

It is not likely, however, that such an injunction would prevent distribution
of the whole distro, or even of an entire package.  More likely, a feature or
set of features, would have to be disabled, modified so that the software no
longer infringes, or removed entirely, in the country where the finding of
patent infringement was made.

Further, designing around the patent claims at stake can prevent even a feature
or features from being removed.  Once even one element of a patent claim is no
longer being practiced, as we have said, the patent claim is no longer
infringed.  In US patent litigation, the crucial moment of definition occurs in
what is called a <q><em>Markman</em> hearing</q>, after which the trial court gives a
definitive ruling on what the patent claims at issue mean for the purposes of
that lawsuit.  Once a <em>Markman</em> hearing has happened, and the scope of the
asserted claims have been narrowly and conclusively defined, it becomes much
easier to design around.


What are damages?
---------------------------------------------------------------------------------

In patent law, damages are money awarded by the court to the plaintiff when the
defendant has been found liable for patent infringement. While the law provides
no maximum damages for patent infringement, it does provide a minimum--the
reasonable royalty for the use made of the invention by the
infringer. Additionally, the court may increase the damages, up to three times
the actual damages, in cases of willful infringement.


What is willful infringement?
---------------------------------------------------------------------------------

Infringement is willful if the infringer knew of the patent, unless the
infringer had a good faith belief that the patent was invalid, or that his
conduct did not infringe.  The patent holder must show all the elements of
willfulness, and in the US courts must do so at a higher standard of proof,
which is called <q>clear and convincing evidence</q>.


I had no prior knowledge of a patent, can I still be held liable?
---------------------------------------------------------------------------------

Knowledge of a patent is not in general required if the party is charged with
direct infringement.  To be found liable for inducing or contributing to
infringement, as we have said, knowledge of the patent or specific efforts to
avoid learning of the patent is required.

In practice, patent holders usually request those they believe infringe to take
licenses.  If the party takes the license offered, the holder gets royalties
without suing for them.  If the party declines the license, the patent holder
has put them on notice, and is therefore in a position to claim intentional
infringement, which results in higher damages and the possibility of recovering
attorney's fees.  It is likely but not certain that before any community-based
distribution is sued for patent infringement, it will receive at least one
letter demanding that a license be taken.


What if the infringement was accidental, inadvertent and unintentional?
---------------------------------------------------------------------------------

An unintentional or inadvertent infringement cannot be willful, as we said
above.  Nor can one contribute to or induce an infringement accidentally, as
knowledge and intention are both required.  But one could be liable for direct
infringement, without knowledge or intention, by using or selling or making or
having made infringing software without more.


How do I become aware of the existence of a patent?
---------------------------------------------------------------------------------

There are innumerable ways by which you may become aware of the existence of a
specific patent.  Aside from being directly contacted by a patent holder, you
may learn about a particular patent through a web search or mailing list, or in
connection with your employment, etc.  If you do become aware of a patent that
concerns you, it is best that you speak to an attorney, rather than share such
knowledge or speculation in a public forum.


What are the defenses available in a patent infringement action?
---------------------------------------------------------------------------------

First, there may be many defenses specific to the facts and circumstances of a
particular situation, and it is the lawyer's job to spot and develop those
defenses.  Some defenses are or may be present in most cases, and they include:

Permission: You are not liable for infringement if you have permission to use
the claims.  Such permission could be explicit.  An explicit permission is
called a <q>license</q>.  Permission can also be implicit: it can result from
conduct or statements by the patent holder which appeared to constitute
permission and on which you relied.  (Lawyers call this <q>estoppel</q>.)  It can
also result from sheer inaction by the patent holder, who can effectively
permit infringing conduct by <q>going to sleep on its rights</q>, which lawyers call
<q>laches</q>.

Non-Infringement: A non-infringement determination is a showing that none of
the patent claims actually <q>read on</q> the software charged. In other words, the
software does not actually implement every element of what is recited in any
claim.

Invalidity: If the patent is invalid, it cannot be infringed.  Invalidity can
be shown by proving that the subject matter of the patent is outside the scope
of patent law.  It can also be shown by demonstrating, under US law, that the
patent is <q>non-novel</q> or <q>obvious</q>.  Under patent law, in order for a patent to
be valid, the claimed invention must have been useful, reducible to practice,
novel, and non-obvious to a <q>person having ordinary skill in the art</q> at the
time that the invention was made. An invalidity defense, therefore, shows that
the patent failed to meet one of these requirements.

<h1>The patent risk to a community distribution

Can you provide examples of patent infringement suits against FOSS communities?
---------------------------------------------------------------------------------

No.  Fortunately, few such cases exist, and none has yet developed to final
judgment.  To date, no court has ever addressed most of the issues unique to
free software distribution. We believe that this is because FOSS communities do
not have <q>deep pockets</q> from which to pay royalties, and suing individual
developers who do not have large revenues makes bad press for patent holders
without achieving any useful outcome.


We are a FOSS distribution and we don't make any money.  How will we pay damages if they are awarded against us?
------------------------------------------------------------------------------------------------------------------------

This question, like all other similar questions about the legal risks and
responsibilities of projects, depends very much on the details of their legal
structure and commercial relations.  There is no general answer about how
projects deal with their legal risks, including the risks of damages judgments
for patent infringement or other liabilities.
`SFLC <http://www.softwarefreedom.org">`_,
the `Software Freedom Conservancy <http://sfconservancy.org/">`_,
the `Apache Software Foundation <https://www.apache.org/">`_,
the `Free Software Foundation <http://www.fsf.org">`_,
`Software in the Public Interest <http://www.spi-inc.org/>`_
and other organizations help projects to fit
within legal contexts and organizations that can usefully address these
questions at a general level.  If your distribution or a project within your
distribution believes that it faces potential legal liability, you should
consult us or one of the other organizations named.

We are a FOSS distribution and we make money. Does that make us more susceptible to a patent infringement suit?
------------------------------------------------------------------------------------------------------------------------

Anyone making revenue is a more attractive target for a patent holder to sue
than someone who makes no money out of which damages could be paid.  A
community distribution that has absolutely no revenue is not an attractive
target.  But even if you make a few hundred thousand dollars a year in sales,
compared to a profit-making enterprise the size of Microsoft, or even Red Hat,
you are not worth the expenses of litigation to a patent troll or other
rational plaintiff.

I have heard that distributing source code is safer than distributing object code. Is that true?
-----------------------------------------------------------------------------------------------------------

Yes.  Distributing source code is probably safer than distributing binaries,
for a few reasons.  First, source code, like the patent disclosures themselves,
teaches how the invention works, rather than being the invention.  If source
code standing alone can infringe the patent, it is difficult to understand how
handing out photocopies of the patent itself wouldn't infringe.  Second, in the
US, courts <em>may</em> find source code to be speech, as we believe they should find,
thus making source code subject to First Amendment protection.  We know little
about how the Supreme Court would harmonize the patent law with First Amendment
requirements.  We at SFLC have written several briefs in the Supreme Court
addressing these issues, but the Court has never reached or decided them.
Furthermore, as mentioned above, liability for patent infringement can be
imposed where one enables or encourages another to infringe a patent, but the
requirements of knowledge and intent are more strict in secondary liability
situations. Because a user must first compile the source code and install the
software in order to infringe, a court is less likely to hold the community
liable for inducing or contributing to the infringement.

As part of a community distribution project, who is most likely to get sued for patent infringement?
---------------------------------------------------------------------------------

This is a problem for the potential patent aggressor, more than for the
distribution.  A community distribution comprised by volunteers, without any
hierarchical structure of employment or supervision, cannot be sued by suing
<q>the head</q>.  If infringement requires intent and knowledge or specific efforts
not to know, as it does in cases of inducing or contributing to infringement,
the individual with such intent and knowledge must probably be found and sued
in his own person.  If people who write code and documentation don't read
patents, and the volunteers who develop code for a package do not maintain the
same package or a related package, the aggressor may find it difficult to sue
anybody at all.

The specifics of any given situation, however, will undoubtedly be crucial.  As
with all other matters of the kind, if you believe a patent is likely to be
asserted against your distribution or its volunteers, you should contact SFLC
or another lawyer immediately.

Are you suggesting that it is better for developers and contributors not to read patents? If yes, why?
-----------------------------------------------------------------------------------------------------------

Yes. Unfortunately, U.S. patent law creates disincentives for searching through
patents, even though one of the main justifications given for the patent system
is that the patent teaches the public how to practice an invention that might
otherwise be secret.  <q>Willful</q> infringement subjects the infringer to enhanced
damages when they are aware of the patent and intend to infringe, and reading
patents increases the probability that subsequent infringement will be found to
be willful. Moreover, we find that developers often assume that the patents
they discover are broader in scope than they actually are, and thus such
developers become overly or needlessly worried. If, despite this, you do intend
to conduct a patent search, you should seek legal advice first.


I am outside the United States. Do I have anything to worry about?
---------------------------------------------------------------------------------

Although most countries are members of the World Intellectual Property
Organization (WIPO) as well as signatories to the Patent Cooperation Treaty
(PCT), large corporations generally restrict their patent acquisition
activities to the <q>Big Three</q>: the US, EU, and Japan. This is considered
sufficient protection for most companies, although companies are increasingly
filing patent applications in China with the hope that patent rights will
eventually be adequately respected by the government and business
communities. In addition, large multi-national corporations in other
jurisdictions, such as Korea and Canada, will usually file patent applications
in their own countries before filing patent applications internationally.  In
India, some software has been patented despite the clear statutory declaration
that software *per se* is unpatentable.  SFLC in India has begun challenging
such patents.

But regardless of where you work, software that infringes patents cannot be
imported into countries where those patents have issued, which means that you
must at least be concerned about the ability to reach your intended users.

As always, consultation with a local lawyer is a good step if you have any
questions about your situation or liabilities.


Are there any guidelines to limit our risk of patent infringement?
---------------------------------------------------------------------------------

Yes.  This document is meant to educate about patent risk, and while it is
difficult to give advice regarding every reader's specific situation, there are
a few guidelines that may be extracted.

 * Reading patents, especially when researching how to design a contribution to
   your free software project, may expose communities to liability that they
   would not otherwise have.
 * Parts of a free software community that distribute source code and not object
   code probably have slightly less patent risk.
 * Distributing free software commercially is probably more risky than
   distributing software gratis.
 * Having the ability to remove features and packages quickly and easily from
   distribution will help mitigate any damages the community could incur.
 * Patent litigation is not an amateur sport.  If you are contacted by anyone
   threatening to assert a patent against you, contact the Software Freedom Law
   Center or another qualified attorney as soon as possible.


<hr />

**Acknowledgements.** This document has been prepared by lawyers at SFLC, with
inputs from Stefano Zacchiroli, on behalf of the Debian Project.
