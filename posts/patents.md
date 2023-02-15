# Patents and open-source Software

1. [Introduction](#introduction)
2. [Summary](#summary)
3. [Patent Exhaustion](#patent-exhaustion)
4. [Patent Clauses in open-source Licenses](#patent-clauses-in-open-source-licenses)
5. [Remaining Questions](#remaining-questions)

To expand on the earlier article on GPL licensing, I did a read up on patents in open-source software which I present here. Feel free to email me any comments or corrections (e@ this domain).\
_Eliot Roxbergh 2021-06-09_

## Introduction

Patents, unlike copyright, aims to protect an invention (i.e. an underlying logic) as opposed to a specific implementation (i.e. work).
In this article, I refer to US law. Where, from what I understand, software patents are more broad and powerful than in the EU.
Software patents are controversial, but that is a topic for another time.


Initially, my questions were i) why are companies seemingly hesitant to contribute to open-source software from an intellectual property perspective? Considering most companies in some way use open-source software, to then share their changes upstream could benefit them by lowering their technical debt.
And ii) what is the risk for a consumer of open-source software to be liable, mainly does a party absolve its patent rights by distributing a work under an open-source license?
To partially answer both these questions, I present two possible defenses explaining why patent rights are usually not enforeable for the work distributed by a patent holder.
In short, these reasons are patent exhaustion as well as the rights given in the software license.


Comment regarding the EU;
In the European Union, "programs for computers" are said to be not patentable, but in practice, certain software patents are both present and enforceable [1] (although seemingly more limited than in the US [2]).¹
Still, the general ideas presented here apply.
Ideas, such as, patent exhaustion as well as you cannot expect to sue your users for behavior that you clearly allow in the license (i.e. an implicit patent clause).
The issues with software patents are also said to be less severe in the EU [2], partly since it is harder for patent trolls to operate, as they need to pay legal costs if the suit is lost [3].

¹ _More on this here: <https://www.bardehle.com/europeansoftwarepatents/software-patent-epo/> (and also <https://en.wikipedia.org/wiki/Software_patents_under_the_European_Patent_Convention>)._

[1] - <https://fsfe.org/activities/swpat/swpat.en.html>, <https://www.epo.org/law-practice/legal-texts/html/epc/2020/e/ar52.html>

[2] - <https://startupxplore.com/en/blog/startup-patents-in-europe/>, <https://thenextweb.com/news/how-the-us-patent-mess-affects-european-tech-and-startups>

[3] - Voet, Milan, Trolling the U.S. and EU Patent System: Solved by a Loser-Pays-Attorney-Fees Regime? (May 4, 2018). Available at SSRN: <https://ssrn.com/abstract=3463481>


## Summary

As one could expect, it is not possible to give a complete answer on patent law for open-source software as this depends on, for instance, the jurisdiction and potentially the license text in question. 
Still, it is true that if a patent holder distribute a work, they should not be able to sue legitimate users for patent infringement.
The two possible defenses are patent exhaustion and an interpreted patent license (implicit or explicit) from the software license [1].

Firstly, the idea behind patent exhaustion, is that the patent holder should not profit more than once for the transfer of a good [2].
Therefore, distributing a work (including as open source¹) exhausts the patent.
So, by providing a work as open source, it makes the patent holder's relevant patents harder to enforce (as someone could then reuse the open-source code to circumvent the patents).
Moreover, patent exhaustion could also extend to (re)distribution, which risks limiting the patent's enforceability, even if the patent holder only redistribute another's work.
In other words, the patent holder lose some rights to enforce patents to the benefit of the users, for the work conveyed as open-source (regardless if it is theirs or not).


<!--- In general, there is no definitive answer, as these questions highly depend on the jurisdiction and earlier case law. -->
Secondly, if a software license provides certain rights, such as to use and modify the software, it would be hard for the author to argue that a patent they hold could then restrict these rights they have specifically granted.
That is, an implicit patent license can generally be assumed for the agreed use, as stated in the software license.
The exact wording in the software license is thus also very important.
However, as long as the (implicit patent clause) interpretation has not been tested in court, it will not be completely certain.
This is why some modern licenses (such as GPLv3, discussed later) include a clause that explicitly grants a patent license to its users.

<!--- However, if the implicit clause is not recognized, it is entirely possible to use other defenses, such as claiming that the holder exhausted their patent license when distributing the software, as mentioned above. -->

<!--- Additionally, some licenses provide a patent retaliation clause to further discourage legal action against its users from anyone using the software. -->

<!--- TODO would be good with a conclusion here -->

¹ As I use the term here, open-source software must fulfill two requirements: software (1) whose source code is available and (2) whose license allows its users to use, modify and redistribute this code (and binaries, if included). Not to be confused with source-available software, that is, software whose code is available to view but without these additional rights.
Arguably, open-source software does not need to be free of charge. However, when I write here, I have gratis open-source software in mind. For a quick reference, [Wikipedia](https://en.wikipedia.org/wiki/Open-source_software) on open-source software, _"software that is released under a license in which the copyright holder grants users the rights to use, study, change, and distribute the software and its source code to anyone and for any purpose [..]  software that is by definition licensed free of charge"_.

[1] - <https://www.elgaronline.com/view/journals/qmjip/8-3/qmjip.2018.03.03.xml>, <https://www.ipmvs.com/news/the-federal-circuit-defines-implied-licenses-and-examines-exhaustion-doctrine/>

[2] - <https://lwn.net/Articles/780078/>, <https://archive.fosdem.org/2019/schedule/event/patent_exhaustion/>


## Patent Exhaustion

A possible defense is to argue patent exhaustion (regardless of the software license).
Namely, if a patent holder, sell or otherwise distribute a work covered by their patent, the patent is exhausted. Then it is no longer possible for them to sue for patent infringement for that conveyed work.
This also applies for open-source distribution, so that if the work is released as such, they may not sue the users for patent infringement [1][2].
With patent exhaustion, note that the patent is still in effect and enforceable, however just not when it comes to the distributed work in question.
<!---  question: are there limits to patent exhaustion, does this hold for all possible uses of the work? -->

Taking patent exhaustion further, it could also apply for redistribution.
This is an important point, since for instance, if a company redistribute a large project like Linux, it should be that they exhaust all their related patents by doing so.
Moreover, if a company clone a Git repo, make some changes, and then make a pull request.
Then, this could count as redistribution which would exhaust any patents applicable for the complete repository (at least James Bottomley argues this in his blog [2]).
For these reasons, patent exhaustion could indeed be why some companies are hesitant to contribute to open-source projects.
More on patent exhaustion here [1][2].

[1] - <https://lwn.net/Articles/780078/>, <https://archive.fosdem.org/2019/schedule/event/patent_exhaustion/>

[2] - <https://blog.hansenpartnership.com/a-roadmap-for-eliminating-patents-in-open-source/>


## Patent Clauses in open-source Licenses


Other defenses could be based on the rights granted in the provided software license.
To make it absolutely clear, the license can state that its users receive a patent license for the covered work, this is what is called an _explicit patent clause_.
However, even if such a clause is not included, the license can still provide assurances (not to be confused with patent exhaustion) in the form of an implied patent license for the user;
Open-source licenses state that the users of the software are given several rights, and if a patent license would be required to practice these rights, such a license can be implied (as this behavior was specifically allowed by the patent holder as per the license) [3].
Therefore, the licensee should be allowed to freely use and distribute the covered work (according to the terms of the license) even if the open-source license does not mention patents specifically.
Examples of an _implicit patent clause_ can be seen in the MIT license [2] or in the here stronger GPLv2 license, as these do not explicitly mention that a patent license is given to the user. [1]

The less clear the license is regarding patents, the higher the risk that the implied patent license defense is not recognized for some reason (although this should suffice for most cases in the US, for instance [2][1]) or that the extent of this patent license is insufficient as there might be certain edge cases [4][1][3].
Another question is to what extent an implicit patent clause has been tested in court, as it otherwise makes the situation uncertain [1].¹
For these reasons, some licenses provide an explicit patent clause to avoid depending on an implicit interpretation, as seen in GPLv3 and Apache.
In these licenses, it is stated explicitly that the patent holder grants a patent license for use according to the terms of the license.²
That being said, the implicit clause in e.g. GPLv2, still provides protection in many cases and jurisdictions [3].
In a 2006 talk, Richard Stallman states that an explicit patent clause was added since the clause in GPLv2 was not sufficient in all countries and that _"[the explicit patent license in GPLv3] is pretty much the same as the implicit patent licence that US law gives people"_ [9].


Regardless of patents, the work is still naturally covered by copyright, and its license may put additional restrictions thereon.
For instance, if the patent holder distributes the patented work under GPLv3, for a licensee to then utilize the granted patent license in their own work it must constitute a derived work, and thus also be licensed under GPLv3 (as is one of the requirements of the GPLv3 license).
Otherwise, no patent rights are given, and the holder may choose to enforce the patent (remember that both patent exhaustion and a patent clause only gives rights when handling the conveyed work in question).³ [8]

Since an open-source license should allow for redistribution and modification, anyone could, in theory, then use, sell, and modify that patented code legally.
So by the nature of open source, someone could potentially extract and modify the patented code and use it (i.e. the derivative work) themselves, without infringing on any patents held by the authors (or on the software license). Although from a patent viewpoint, this could in some ways be restricted depending on the interpretation of the patent license granted by the license, where an explicit patent clause could provide stronger rights.⁴

Comment; This article discusses defenses regarding the implicit patent license of GPLv2: _<https://assets.fenwick.com/legacy/FenwickDocuments/potential_defenses.pdf>_

¹ _There are not many court cases regarding GPLv2's implicit patent clause. For instance, there is a case from the US (XimpleWare/Versata 2013-2015) [10], but the situation is still not entirely clear._

² _More than that, GPLv3 states that a contributor authorizes use under this license for the contents of its "contributor version", referring to the whole GPL-licensed work. So just by distributing a GPLv3 work, the patent holder grants a patent license for the complete work (and not only for any modifications made) - specifically a "non-exclusive, worldwide, royalty-free patent license under the contributor's essential patent claims, to make, use, sell, offer for sale, import and otherwise run, modify and propagate  the contents of its contributor version." (from GPLv3 section 11)_. _Also mentioned here on slide 18 <https://www.ipa.go.jp/files/000028295.pdf> (Eben Moglen, GPL3: Process and Product, 21 December 2007)_.

³ _Discussed more in-depth here <https://opensource.com/article/18/3/patent-grant-mit-license> ([2])._

⁴ _For instance, it is not as clear if the licensee changes or adds directly to the patented code, whether that addition is covered by the implied patent license they have received. Mentioned here regarding GPLv2 in the EU: <http://en.swpat.org/wiki/Implicit_patent_licence#European_Union>._


#### Patent Retaliation in GPLv3

On another note, some licenses also include a so-called _patent retaliation clause_, this penalizes a user (of the software) who would sue a contributor (i.e. author) or another user of the open-source project for patent infringement.
In which case, the license is terminated and the plaintiff (i.e. the suing party) loses all their rights under the license including any patent licenses granted [7].¹

Two examples of licenses that include a patent retaliation clause are Apache and GPLv3.²
GPLv3 states that you may not impose any restrictions on the rights granted by the license, and if you violate the license, your rights provided by the license are terminated [6].
Here, they also specifically mention that _"you may not initiate litigation [..] alleging that any patent claim is infringed by making, using, selling, offering for sale, or importing the Program or any portion of it"_.
Regarding the explicit patent clause, GPLv3 states that every recipient is given the patent license necessary to exercise _all rights_ provided by the license [5].


¹ _Although, arguably, they may still use the software, considering GPLv3 states: "You are not required to accept this License in order to receive or run a copy of the Program"_

² _As usual, it varies depending on the wording in the license. A comparison of patent retaliation clauses is presented here, pp. 15-38 <http://people.apache.org/~cliffs/apacheconEU2007-schmidt-spectrum.pdf> (Cliff Schmidt, 2007)_

#### Examples from the GPLv3, GPLv2, and MIT Licenses

Here follows small excerpts from the main licenses mentioned earlier, as relevant for patent licenses.\
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

[9] - <https://fsfe.org/activities/gplv3/tokyo-rms-transcript.en.html>

[10] - HAAPANEN, Anna Kaarina. Free and Open Source Software and the Mystery of Software Patent Licenses Under the GPL. Journal of Open Law, Technology & Society, [S.l.], v. 7, n. 1, p. 19-28, dec. 2015. ISSN 2666-8106. Available at: <https://www.jolts.world/index.php/jolts/article/view/107>. Date accessed: 15 feb. 2023. 

## Remaining Questions

One aspect I have not considered here, is how a patent suit would play out in practice. For instance, a party should have been able to provide a legitimate defense based on patent exhaustion, but nevertheless be forced into accepting a settlement due to high legal costs. This, to some degree, is a reality since patent trolls do exist, thanks to cases like this.

Another question; if an open-source project infringes on a patent, who is held liable?
Anyone can in theory be sued (such as the author, distributor, or user), and this in practice largely depends on who has the money [1].
However, do some licenses "change" (or make clearer) who is liable for patent infringement?
For instance, does the patent clause in GPLv3 or Apache make a difference here?
Reading the GPLv3, I did not find any direct mention of this.¹
And to the contrary, by distributing a work under _any_ license I would assume you are more likely to be liable than a mere user of the software.
Consider that (from my understanding) the software license is a legal contract between the (e.g.) author and the user.
Therefore, to then license this work without (copyright or patent) rights would undoubtedly be problematic for the licensor, especially if they are doing so knowingly.
We also see this reflected in the wording of GPLv3, _"A "contributor" is a copyright holder who authorizes use under this License"_.


<!--- Question: What does this mean in GPLv3? "You are not responsible for enforcing compliance by third parties with this License." TODO -->
¹ At first I thought the following paragraph could be relevant, _"If you convey a covered work, knowingly relying on a patent license and the Corresponding Source of the work is not available for anyone to copy, free of charge and under the terms of this License [...]"_. However, this is referred to as the _downstream shielding provision_ and not relevant for our question (because as I understand, "relying on" means that you in some way benefit from a patent license). Clarification from Richard Stallman, _"We were already concerned about [..] the possibility that a distributor might receive a patent licence which did not explicitly impose limits on downstream recipients but simply failed to protect them. What if one company pays Microsoft for a patent licence where Microsoft says "Alright, we won't sue you, but we're just not making any promises about your customers if they redistribute it". We had already written a downstream shielding provision into GPL version 3 saying that if you convey the program, and you are benefitting from a patent licence that is not available, that does not extend to the downstream users, then you have to do something to shield them."_ - _<https://fsfe.org/activities/gplv3/tokyo-rms-transcript.en.html>_

[1] - <https://ocpatentlawyer.com/everyone-in-the-supply-chain-could-be-sued-for-patent-infringement/>
