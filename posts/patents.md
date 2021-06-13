# Short on Patents

To expand on the earlier post on licensing, I did a read up on patents which I present here. I am not a lawyer, and this is not legal advice.

Patents unlike copyright, aims to protect an "invention" as opposed to a specific work.
From what I understand, software patents are more broad and powerful in the US than e.g. in the EU.
As usual, in practice patents depend heavily on the jurisdiction and below I refer to US law.
Software patents are quite controversial, but that is a topic for another time.\
_Eliot Roxbergh 2021-06-09_

Comment regarding the EU;
In the European Union, "programs for computers" are said to be not patentable, but in practice (certain) software patents are both present and enforceable [1].¹
Regardless, it is more limited than in the US [2].

¹ _More on this here: <https://www.bardehle.com/europeansoftwarepatents/software-patent-epo/> (and also <https://en.wikipedia.org/wiki/Software_patents_under_the_European_Patent_Convention>)._


[1] - <https://fsfe.org/activities/swpat/swpat.en.html>, <https://www.epo.org/law-practice/legal-texts/html/epc/2020/e/ar52.html>

[2] - <https://startupxplore.com/en/blog/startup-patents-in-europe/>, <https://thenextweb.com/news/how-the-us-patent-mess-affects-european-tech-and-startups>


## Patent Exhaustion

If you as a patent holder, sell or otherwise distribute a work covered by your patent, the patent is exhausted; then it is no longer possible to sue for patent infringement for that conveyed work.
This also extends to open source, so that if your work is open sourced you may not sue the users for patent infringement [1].
Since an open source license should allow redistribution and modification, anyone could in theory then use, sell, and modify that patented code legally.
Consequently, patent exhaustion could be a reason why some companies are hesitant to contribute to open-source projects.

With patent exhaustion, note that the patent is still in effect and enforceable, however just not when it comes to the distributed work in question.
Regardless, due to the nature of open source, someone could potentially extract and modify the patented code and use it (the derivative work) themselves without infringing on any patents you hold (or the license). Although from a patent viewpoint this could be restricted depending on the interpretation of the patent license granted by the license.¹
Moreover, the work is still obviously covered by copyright, and its license may put additional restrictions thereon.
For instance, if the patent holder distributes the patented work under GPLv3, for someone (i.e. a licensee) to then utilize the granted patent license in their own work it must constitute a derived work and thus also be licensed under GPLv3.
Otherwise, no patent rights are given and the holder may enforce the patent.² [2]


Taking patent exhaustion further, it might apply for redistribution
(e.g. if a company redistributes a large project like Linux could they exhaust all their related patents?),
or if the company for instance clone a Git repo, make some changes, and then make a pull request
(does this count as redistribution which would exhaust any patents applicable for the complete repository, or only for the specific change made?).
Something to keep in mind, more on this here [1].

Comment; In this slightly dated article, patent exhaustion and more defenses are discussed for an accused infringer: 
_<https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>_

¹ _For instance it is not as clear if the licensee changes or adds directly to the patented code, whether that addition is covered by the patent license they have received. Mentioned here regarding GPLv2 in the EU: <http://en.swpat.org/wiki/Implicit_patent_licence#European_Union>._

² _Discussed more in-depth here: [2]._


[1] - <https://blog.hansenpartnership.com/a-roadmap-for-eliminating-patents-in-open-source/>, <https://lwn.net/Articles/780078/>

[2] - <https://assets.fenwick.com/legacy/FenwickDocuments/IP_Bulletin_Summer_2006.pdf>_


## Patent Clauses in open-source Licenses

Software licenses can mention patents, but not all do.
However, these licenses can still provide assurances (in the form of an implied patent license) for the user even when not explicitly stated.
Open-source licenses state that the users of the software are given several rights, and usually to practice these rights a patent license would be required. Therefore a patent license is implied, as this behavior was specifically allowed by the patent holder as per the license. [3]
Examples of an _implicit patent clause_ can be seen in the MIT license [2] or in the here stronger GPLv2 license, as these do not explicitly mention that a patent license is given to the user. [1]

However, the less clear the license is regarding patents, the higher the risk that the implied patent license defense is not recognized for some reason (although this should suffice for most cases in the US for instance [2][1]).
For this reason, some licenses provide an explicit patent clause to avoid depending on an implicit interpretation, as seen in GPLv3 and Apache.

Additionally, some licenses (such as the aforementioned: GPLv3 and Apache) also include a so-called _patent retaliation clause_.
A patent retaliation clause, is a clause that penalizes a user who would sue a contributor (i.e. author) of the open source project.
In which case, the license is terminated and the plaintiff (the user) loses all their rights under the license including any patents granted [7].

### Implicit Clause

As described earlier, due to an implied patent license (where patent exhaustion applies), the licensee is often allowed to freely use and distribute the covered work even if the open-source license does not mention patents specifically.
Still, it is beneficial to have an explicit patent clause in the license, i.e. in writing from the patent holder that a patent license is granted.
This is mainly true since patent exhaustion, as well as the interpretation and validity of implicit clauses, may differ between jurisdictions - and there could be certain edge cases [4][1][3].
Another question is whether an implicit patent clause has been tested in court, otherwise it makes the situation uncertain [1].¹
That being said, patent exhaustion and the implicit clause in e.g. GPLv2 still provide protection in many cases and jurisdictions [3].

### Patent Retaliation in GPLv3

GPLv3 states that every recipient is given the patent license necessary to exercise _all rights_ provided by the license (i.e explicit patent clause) [5].
Additionally, you may not impose any restrictions on the rights granted by the license, and if you violate the license your rights provided by the license are terminated [6].
As we see in the latter statement, GPLv3 provides a patent retailiation clause that if you in anyway restrict the users' rights your license is terminated.
This would for instance apply if you sue for patent infringement.

### Examples from the GPLv3, GPLv2, and MIT Licenses

Here follows small excerpts from the main licenses mentioned earlier relating to patent licenses,\
In GPLv3 we have the explicit statement;\
_"Each contributor grants you a non-exclusive, worldwide, royalty-free patent license under the contributor's essential patent claims, to make, use, sell, offer for sale, import and otherwise run, modify and propagate the contents of its contributor version."_ [6]

GPLv2 has an implicit statement (which does not specifically mention that users receive a patent license);\
_"if a patent license would not permit royalty-free redistribution of the Program by all those who receive copies directly or indirectly through you, then the only way you could satisfy both it and this License would be to refrain entirely from distribution of the Program."_ [4]

Finally in MIT, we see an even weaker implicit statement which does not mention patents at all;\
_"Permission is hereby granted [..] to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so"_ [2]


¹ _I was unable to find any case testing the interpretation of GPLv2's implicit patent clause, but one would think such a case should exist thus shedding some light on this question._


[1] - http://en.swpat.org/wiki/Implicit_patent_licence

[2] - https://opensource.com/article/18/3/patent-grant-mit-license

[3] - <https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>

[4] - <http://www.gnu.org/licenses/gpl-faq.html#v2OrLaterPatentLicense>

> GPLv2 implicit patent license: \
> _"You may not impose any further restrictions on the recipients' exercise of the rights granted herein._"\
> _"if a patent license would not permit royalty-free redistribution of the Program by all those who receive copies directly or indirectly through you, then the only way you could satisfy both it and this License would be to refrain entirely from distribution of the Program."_\
> <https://www.gnu.org/licenses/old-licenses/gpl-2.0.html> (and mentioned here: <https://news.ycombinator.com/item?id=1978507>)

[5] - <https://www.gnu.org/licenses/quick-guide-gplv3.html>

> _"Whenever someone conveys software covered by GPLv3 that they've written or modified, they must provide every recipient with any patent licenses necessary to exercise the rights that the GPL gives them. In addition to that, if any licensee tries to use a patent suit to stop another user from exercising those rights, their license will be terminated."_

[6] - <https://www.gnu.org/licenses/gpl-3.0.en.html>

[7] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

> _"In effect, yes. Section 10 prohibits people who convey the software from filing patent suits against other licensees. If someone did so anyway, section 8 explains how they would lose their license and any patent licenses that accompanied it."_



## Question: Who can get Sued for Infringement

Question, if an open source project infringes on a patent who is liable?
Anyone could in theory be sued [1],
but does the patent clauses of GPLv3, Apache, etc. make a difference here?

Reading GPLv3, the only mention I can find is _"If you convey a covered work, knowingly relying on a patent license"_, which is a special case.


[1] - <https://ocpatentlawyer.com/everyone-in-the-supply-chain-could-be-sued-for-patent-infringement/>
