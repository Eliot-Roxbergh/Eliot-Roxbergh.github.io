# Short on Patents

To expand on the earlier article on licensing, I did a read up on patents which I present here. I am not a lawyer, this is not legal advice, and I might be wrong.\
_Eliot Roxbergh 2021-06-09_


Patents, unlike copyright, aims to protect an invention (i.e. an underlying logic) as opposed to a specific implementation (i.e. work).
In this article, I refer to US law. Where, from what I understand, software patents are more broad and powerful than in the EU.
Software patents are controversial, but that is a topic for another time.


Comment regarding the EU;
In the European Union, "programs for computers" are said to be not patentable, but in practice, (certain) software patents are both present and enforceable [2] (although seemingly more limited than in the US [3]).¹
Still, the general ideas presented here apply.
Namely, we have patent exhaustion as well as you cannot expect to sue your users for behavior that you clearly allow in the license (i.e. implicit patent clause).
The issues with software patents are also less severe [3], partly since it is harder for patent trolls to operate, as they need to pay legal costs if the suit is lost [4].

##### Background

Initially, my questions were i) why are companies sometimes hesitant to contribute to open-source software from an intellectual property perspective? Considering many (if not all) companies in some way use such software, to then share their changes upstream could lower their technical debt.
And ii) what is the risk for a consumer of open-source software to be liable, mainly does a party absolve its patent rights by distributing a work under an open-source license.

##### Summary

If a patent holder distributes a work, they should not be able to sue legitimate users for patent infringement: two possible defenses are patent exhaustion and an interpreted patent clause (implicit or explicit) from the software license [1].
Moreover, patent exhaustion also extends to (re)distribution, which risks limiting the patent's enforceability, and not only for the most obvious cases.
In other words, the author(s) lose some rights to enforce patents to the benefit of the users when conveying their work open-source (note that this only applies for the work distributed, the patent is still enforceable otherwise).
So this could then, in some cases, make a company's patents harder to enforce.
Additionally, some licenses provide a patent retaliation clause to further discourage legal action against its users from anyone using the software.

As a computer professional not educated in law, the situation is not as clear-cut or general as I wanted to believe. Instead, it highly depends on the jurisdiction and the license text in question. If the license provides certain rights, such as to use and modify the software, it would be hard for the author to argue that a patent they hold could then restrict those rights they have explicitly granted (i.e. an implicit patent license can generally be assumed for the allowed use, as stated in the software license).
Still, it is not entirely certain in all jurisdictions, and it is beneficial to be as clear as possible. For instance, one might interpret a legislation as recognizing an implicit patent clause, but it could be uncertain until such a case has been tested in court.
This is why some modern licenses include a clause that explicitly grants a patent license to the users.
However, if the implicit clause is not recognized, it is entirely possible to use other defenses, such as claiming that the holder exhausted their patent license when distributing the software.

##### Remaining Questions

One aspect I have not considered here, is how a patent suit would play out in practice. Perhaps, in theory, a party could be able to provide a legitimate defense based on patent exhaustion, but still be forced into accepting a settlement due to high legal costs. This, to some degree, is a reality since patent trolls do exist (and mainly in the US), thanks to cases like this.

Another question; if an open-source project infringes on a patent, who is held liable?
Anyone can in theory be sued (e.g. the author, distributor, or user) [5], but does some licenses "change" (or make clearer) who is liable for patent infringement.
So do the patent clauses, in e.g. GPLv3 and Apache, make a difference here?
Reading GPLv3, the only mention I can find is _"If you convey a covered work, knowingly relying on a patent license"_, which, as I understand, is a special case when you yourself are the patent holder.²


¹ _More on this here: <https://www.bardehle.com/europeansoftwarepatents/software-patent-epo/> (and also <https://en.wikipedia.org/wiki/Software_patents_under_the_European_Patent_Convention>)._

² _For your reference, the definition of "convey" from GPLv3: "To "convey" a work means any kind of propagation that enables other parties to make or receive copies. Mere interaction with a user through a computer network, with no transfer of a copy, is not conveying"\- <https://www.gnu.org/licenses/gpl-3.0.html>_

[1] - <https://www.elgaronline.com/view/journals/qmjip/8-3/qmjip.2018.03.03.xml>, <https://www.ipmvs.com/news/the-federal-circuit-defines-implied-licenses-and-examines-exhaustion-doctrine/>

[2] - <https://fsfe.org/activities/swpat/swpat.en.html>, <https://www.epo.org/law-practice/legal-texts/html/epc/2020/e/ar52.html>

[3] - <https://startupxplore.com/en/blog/startup-patents-in-europe/>, <https://thenextweb.com/news/how-the-us-patent-mess-affects-european-tech-and-startups>

[4] - Voet, Milan, Trolling the U.S. and EU Patent System: Solved by a Loser-Pays-Attorney-Fees Regime? (May 4, 2018). Available at SSRN: <https://ssrn.com/abstract=3463481>

[5] - <https://ocpatentlawyer.com/everyone-in-the-supply-chain-could-be-sued-for-patent-infringement/>

## Patent Exhaustion

If a patent holder, sell or otherwise distribute a work covered by their patent, the patent is exhausted. Then it is no longer possible for them to sue for patent infringement for that conveyed work (however, does this hold for all possible uses of the work?).
This also applies for open source distribution, so that if the work is released as such, they may not sue the users for patent infringement [1].
With patent exhaustion, note that the patent is still in effect and enforceable, however just not when it comes to the distributed work in question.

Taking patent exhaustion further, it usually applies for redistribution
(e.g. if a company redistributes a large project like Linux it could be possible that they exhaust all their related patents),
or if the company for instance clone a Git repo, make some changes, and then make a pull request
(however, does this count as redistribution which would exhaust any patents applicable for the complete repository, or only for the specific change made?).
Something to keep in mind, more on this here [1].
For these reasons, patent exhaustion could be why some companies are hesitant to contribute to open-source projects.


[1] - <https://blog.hansenpartnership.com/a-roadmap-for-eliminating-patents-in-open-source/>, <https://lwn.net/Articles/780078/>


## Patent Clauses in open-source Licenses


Software licenses can mention patents, but not all do.
However, these licenses can still provide assurances (in addition to patent exhaustion) in the form of an implied patent license for the user;
Open-source licenses state that the users of the software are given several rights, and if a patent license would be required to practice these rights, such a license can be implied (as this behavior was specifically allowed by the patent holder as per the license) [3].
Therefore, the licensee is allowed to freely use and distribute the covered work even if the open-source license does not mention patents specifically.
Examples of an _implicit patent clause_ can be seen in the MIT license [2] or in the here stronger GPLv2 license, as these do not explicitly mention that a patent license is given to the user. [1]

However, the less clear the license is regarding patents, the higher the risk that the implied patent license defense is not recognized for some reason (although this should suffice for most cases in the US for instance [2][1]) or that the extent of this patent license is insufficient as there might be certain edge cases [4][1][3].
Another question is to what extent an implicit patent clause has been tested in court, as it otherwise makes the situation uncertain [1].¹
For these reasons, some licenses provide an explicit patent clause to avoid depending on an implicit interpretation, as seen in GPLv3 and Apache.
In these licenses, it is stated explicitly that the patent holder grants a patent license for use according to the terms of the license.
That being said, the implicit clause in e.g. GPLv2, still provides protection in many cases and jurisdictions [3].

Regardless of patents, the work is still naturally covered by copyright, and its license may put additional restrictions thereon.
For instance, if the patent holder distributes the patented work under GPLv3, for a licensee to then utilize the granted patent license in their own work it must constitute a derived work, and thus also be licensed under GPLv3 (as is one of the requirements of the GPLv3 license).
Otherwise, no patent rights are given, and the holder may choose to enforce the patent (remember that both patent exhaustion and a patent clause only gives rights when handling the conveyed work in question).² [8]

Since an open-source license should allow for redistribution and modification, anyone could, in theory, then use, sell, and modify that patented code legally.
So by the nature of open source, someone could potentially extract and modify the patented code and use it (i.e. the derivative work) themselves, without infringing on any patents held by the authors (or the software license). Although from a patent viewpoint, this could in some ways be restricted depending on the interpretation of the patent license granted by the license, where an explicit patent clause could provide stronger rights.³

Comment; This article discusses defenses regarding the implicit patent license of GPLv2: _<https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>_

¹ _I could not find any case testing the interpretation of GPLv2's implicit patent clause, but one would think such a case should exist, thus shedding some light on this question._

² _Discussed more in-depth here [2]._

³ _For instance, it is not as clear if the licensee changes or adds directly to the patented code, whether that addition is covered by the implied patent license they have received. Mentioned here regarding GPLv2 in the EU: <http://en.swpat.org/wiki/Implicit_patent_licence#European_Union>._


#### Patent Retaliation in GPLv3

Some licenses also include a so-called _patent retaliation clause_, this penalizes a user who would sue a contributor (i.e. author) of the open source project.
In which case, the license is terminated and the plaintiff (i.e. the user) loses all their rights under the license including any patents granted [7].

Two licenses that include a patent retaliation clause are Apache and GPLv3.
GPLv3 states that every recipient is given the patent license necessary to exercise _all rights_ provided by the license (i.e. an explicit patent clause) [5].
Additionally, it states, you may not impose any restrictions on the rights granted by the license, and if you violate the license, your rights provided by the license are terminated [6].
As we see in the latter statement, GPLv3 provides a patent retaliation clause, so that if anyone restricts the users' rights in any way, their license is terminated.
Something which, for instance, would apply if they sue for patent infringement.

#### Examples from the GPLv3, GPLv2, and MIT Licenses

Here follows small excerpts from the main licenses mentioned earlier, as relevant for patent licenses,\
In GPLv3 we have the explicit statement;\
_"Each contributor grants you a non-exclusive, worldwide, royalty-free patent license under the contributor's essential patent claims, to make, use, sell, offer for sale, import and otherwise run, modify and propagate the contents of its contributor version."_ [6]

GPLv2 has an implicit statement (which does mention patents, but not specifically that users receive a patent license);\
_"if a patent license would not permit royalty-free redistribution of the Program by all those who receive copies directly or indirectly through you, then the only way you could satisfy both it and this License would be to refrain entirely from distribution of the Program."_ [4]

Finally, in MIT, we see an even weaker implicit statement which does not mention patents at all;\
_"Permission is hereby granted [..] to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so"_ [2]



[1] - <http://en.swpat.org/wiki/Implicit_patent_licence>

[2] - <https://opensource.com/article/18/3/patent-grant-mit-license>

[3] - <https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>

[4] - <http://www.gnu.org/licenses/gpl-faq.html#v2OrLaterPatentLicense>

> GPLv2 implicit patent license, see section 6 and 7 <https://www.gnu.org/licenses/old-licenses/gpl-2.0.html> (and mentioned here: <https://news.ycombinator.com/item?id=1978507>)

[5] - <https://www.gnu.org/licenses/quick-guide-gplv3.html>

> _"Whenever someone conveys software covered by GPLv3 that they've written or modified, they must provide every recipient with any patent licenses necessary to exercise the rights that the GPL gives them. In addition to that, if any licensee tries to use a patent suit to stop another user from exercising those rights, their license will be terminated."_

[6] - <https://www.gnu.org/licenses/gpl-3.0.en.html>

[7] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

> _"In effect, yes. Section 10 prohibits people who convey the software from filing patent suits against other licensees. If someone did so anyway, section 8 explains how they would lose their license and any patent licenses that accompanied it."_

[8] - <https://assets.fenwick.com/legacy/FenwickDocuments/IP_Bulletin_Summer_2006.pdf>
