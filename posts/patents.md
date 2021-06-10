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

¹ _More on this here: <https://www.bardehle.com/europeansoftwarepatents/software-patent-epo/>, <https://en.wikipedia.org/wiki/Software_patents_under_the_European_Patent_Convention>_

## Patent Exhaustion

If you sell or otherwise distribute a work covered by a patent, the patent is exhausted; then it is no longer possible to sue for patent infringement for that conveyed work.
This also extends to open source, so that if your work is open sourced you may not sue the users for patent infringement.
Since an open source license should allow redistribution and modification, anyone can then use, sell, and modify that patented code legally.
Consequently, patent exhaustion could be a reason why some companies are afraid to contribute to open-source projects.

Note that the patent is still in effect and enforceable, however not when it comes to the distributed work in question [5].²
Although, due to the nature of open source, someone could potentially extract and modify the patented code and use it (the derivative work) themselves without infringing on any patents you hold (or the license).
The work is still obviously covered by copyright, and its license may put additional restrictions thereon (e.g. the GPL) - but this is not patent law.

Taking this further, exhaustion might apply even for any redistribution
(e.g. if a company redistributes a large project like Linux could they exhaust their related patents?),
or if the company for instance clone a Git repo, make some changes, and then make a pull request
(does this count as redistribution which would exhaust any patents applicable for the complete repository, or only for the specific change made?).
Something to keep in mind. [3]

In [this](https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf) interesting (but dated) article, similar defense is made for an accused infringer and discussed further.
I also found [the article prior](https://assets.fenwick.com/legacy/FenwickDocuments/IP_Bulletin_Summer_2006.pdf) to be interesting [5].

² _Mentioned more in-depth here: <https://assets.fenwick.com/legacy/FenwickDocuments/IP_Bulletin_Summer_2006.pdf>_

## Patent Clause

Some licenses have explicit patent clauses, popular examples include GPLv3 and Apache.
These clauses can be beneficial since it makes it abundantly clear what is and what is not allowed.
Additionally, some licenses (such as the aforementioned) also include a so-called patent retaliation clause.

##### Explicit Clause

Due to patent exhaustion, even if an open-source license does not have a patent clause,
a contributor should not be able to sue the user for patent infringement.
Additionally, certain rights can be provided by the license in an implicit patent clause (see e.g. GPLv2) [5].
Still, it is beneficial to have an explicit patent clause in the license, i.e. in writing from the patent holder.
This is especially true since patent exhaustion, as well as the interpretation and validity of implicit clauses, may differ between jurisdictions [4].
Another question is whether this has been tested in court, otherwise it makes the situation uncertain.
That being said, patent exhaustion and the implicit clause in GPLv2 still provide protection in many cases [5].


##### Patent Retaliation
GPLv3 states that every recipient is given the patent license necessary to exercise _all rights_ provided by the license [6].
Additionally, you may not impose any restrictions on the rights granted by the license, and if you violate the license your rights provided by the license are terminated [7].
The later is often referred to as a _patent retaliation clause_, since if you sue for patent infringement you get penalized [8] - you lose all rights under the license including any patents granted.


## Question: Who can get Sued for Infringement

Question, if an open source project infringes on a patent who is liable?
Does the explicit patent clauses of GPLv3 and Apache make a difference here?

This I don't know, as I understand anyone could _in theory_ be sued [7].
Reading GPLv3, the only mention I can find is _"If you convey a covered work, knowingly relying on a patent license"_, which is a special case.

## Footnotes

[1] - <https://fsfe.org/activities/swpat/swpat.en.html>, <https://www.epo.org/law-practice/legal-texts/html/epc/2020/e/ar52.html>

[2] - <https://startupxplore.com/en/blog/startup-patents-in-europe/>, <https://thenextweb.com/news/how-the-us-patent-mess-affects-european-tech-and-startups>

[3] - <https://blog.hansenpartnership.com/a-roadmap-for-eliminating-patents-in-open-source/>, <https://lwn.net/Articles/780078/>

[4] - <http://www.gnu.org/licenses/gpl-faq.html#v2OrLaterPatentLicense>

[5] - <https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>, https://assets.fenwick.com/legacy/FenwickDocuments/IP_Bulletin_Summer_2006.pdf

> GPLv2 implicit patent license: \
> _"You may not impose any further restrictions on the recipients' exercise of the rights granted herein._"\
> _"if a patent license would not permit royalty-free redistribution of the Program by all those who receive copies directly or indirectly through you, then the only way you could satisfy both it and this License would be to refrain entirely from distribution of the Program."_\
> <https://www.gnu.org/licenses/old-licenses/gpl-2.0.html> (and mentioned here: <https://news.ycombinator.com/item?id=1978507>)

[6] - <https://www.gnu.org/licenses/quick-guide-gplv3.html>

> _"Whenever someone conveys software covered by GPLv3 that they've written or modified, they must provide every recipient with any patent licenses necessary to exercise the rights that the GPL gives them. In addition to that, if any licensee tries to use a patent suit to stop another user from exercising those rights, their license will be terminated."_

[7] - <https://www.gnu.org/licenses/gpl-3.0.en.html>

[8] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

> _"In effect, yes. Section 10 prohibits people who convey the software from filing patent suits against other licensees. If someone did so anyway, section 8 explains how they would lose their license and any patent licenses that accompanied it."_

[7] - <https://ocpatentlawyer.com/everyone-in-the-supply-chain-could-be-sued-for-patent-infringement/>
