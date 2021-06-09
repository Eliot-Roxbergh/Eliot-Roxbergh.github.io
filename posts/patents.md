# Short on Patents

To expand on the earlier post on licensing, I did a read up on patents which I present here. I am not a lawyer, and this is not legal advice.
_Eliot Roxbergh 2021-06-09_

Patents is something different than copyright, as it aims to protect an "invention" as opposed to a specific implementation.
From what I understand, software patents are more broad and powerful in the US than e.g. in the EU.
As usual, in practice patents depend heavily on jurisdiction and below I refer to US law.
Software patents are quite controversial, but that is a topic for another time.


Comment regarding the EU;
In the European Union, "programs for computers" are said to be not patentable. But in practice (certain) software patents are both present and enforceable [1].
Regardless, it is more limited than in the US [2].

## Patent Exhaustion

_Patent exhaustion_ is a major reason why some companies are afraid to contribute to open-source projects _[citation needed]_.
That is, if you sell or otherwise distribute the work covered by a patent, the patent is exhausted.
Basically, it is no longer possible to sue for patent infringement for that work which you distributed.
This also extends to open source, so that if your work is open sourced you may not sue the users.
Since an open source license should allow redistribution and modification, anyone can use, sell, and modify that patented code legally.

Note that (as I understand) the patent is still in effect and enforceable, however not when it comes to the distributed work in question.
Although, due to the nature of open source, someone could potentially extract and modify the patented code and use it themselves without infringing on any patents you hold.
The work is still obviously covered by copyright, and its license (e.g. the GPL) may put additional restrictions thereon - but this is not patent law.

Taking this further, exhaustion might apply even for any redistribution
(e.g. if a company redistributes a large project like Linux could they exhaust a plethora of patents?),
or if the company for instance clones a Git repo, make some changes, and then make a pull request
(does this count as redistribution which would exhaust any patents applicable for the complete repository, and not only for the specific change made?).
Something to keep in mind. [3]

## Patent Clause

Some licenses have an explicit patent clauses, two popular examples are GPLv3 and Apache.
Due to patent exhaustion, even if an open-source license does not have a patent clause,
a contributor should not be able to sue the user for patent infringement.
Still, it is nice to have this in the license, i.e. in writing from the patent holder.

GPL3 states that every recipient is given the patent license necessary to exercise _all rights_ provided by the license [4].
Additionally, you may not impose any restrictions on the rights granted by the license, and if you violate the license your rights provided by the license are terminated including any patents granted [5].
The later is often referred to as a _patent retaliation clause_, since if you sue for patent infringement you get penalized [6] - you lose all rights under the license including any patents granted.

## Who Can Get Sued for Infringement

Question, if an open source project infringes on a patent who is liable?
Does the explicit patent clauses of GPL3 and Apache make a difference here?

This I don't know, as I understand anyone could _in theory_ be sued [7].
Reading GPL3, the only mention I can find is _"If you convey a covered work, knowingly relying on a patent license"_, which is a special case.

## Footnotes

[1] - <https://fsfe.org/activities/swpat/swpat.en.html>, <https://www.epo.org/law-practice/legal-texts/html/epc/2020/e/ar52.html>, <https://en.wikipedia.org/wiki/Software_patents_under_the_European_Patent_Convention>, <https://www.bardehle.com/europeansoftwarepatents/software-patent-epo/>

[2] - <https://startupxplore.com/en/blog/startup-patents-in-europe/>, <https://thenextweb.com/news/how-the-us-patent-mess-affects-european-tech-and-startups>

[3] - <https://blog.hansenpartnership.com/a-roadmap-for-eliminating-patents-in-open-source/>, <https://lwn.net/Articles/780078/>

[4] - <https://www.gnu.org/licenses/quick-guide-gplv3.html>

> "Whenever someone conveys software covered by GPLv3 that they've written or modified, they must provide every recipient with any patent licenses necessary to exercise the rights that the GPL gives them. In addition to that, if any licensee tries to use a patent suit to stop another user from exercising those rights, their license will be terminated."

[5] - <https://www.gnu.org/licenses/gpl-3.0.en.html>

[6] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

> "In effect, yes. Section 10 prohibits people who convey the software from filing patent suits against other licensees. If someone did so anyway, section 8 explains how they would lose their license and any patent licenses that accompanied it."


> Additional reading: \
> http://gplv3.fsf.org/patent-dd2.html \
> https://www.datamation.com/applications/can-you-really-get-sued-for-using-open-source/ \
> https://www.lawoftheledger.com/wp-content/uploads/sites/777/2018/08/Patent-Issues-with-Open-Source-Software-OSS.pdf \
> https://www.morse.law/news/open-source-issues \
> https://opensource.stackexchange.com/questions/7964/why-is-the-apache-license-2-0-patent-license-clause-useful-important \
> https://en.wikipedia.org/wiki/Open_source_license_litigation

[7] - <https://ocpatentlawyer.com/everyone-in-the-supply-chain-could-be-sued-for-patent-infringement/>
