
# GPL Compliance

1. [GPL Main Points](#gpl-main-points)
2. [(L)GPLv2 vs (L)GPLv3](#lgplv2-vs-lgplv3)
3. [How is LGPL Weaker than GPL?](#how-is-lgpl-weaker-than-gpl)
4. [Static vs Dynamic Linking (GPL)](#static-vs-dynamic-linking-gpl)
5. [What is License Compatibility?](#what-is-license-compatibility)

In this article, I have summarized some important things to keep in mind when using a GPL project together with your own work (under any license).
I have focused on GPLv3, but GPLv2, LGPLv2.1, and LGPLv3 are also discussed.
I am not a lawyer and I do recommend reading the relevant licenses - also explained in detail here [1]. Additionally, note that much is still up for debate and depends on jurisdiction and case law.\
_Eliot Roxbergh 2021-01-27_

[1] - <https://copyleft.org/guide/>

Addendum; I use the term _GPL contamination_, referring to situations where using a GPL work incorrectly would legally require you to release your work under the GPL license as well (or stop using GPL work in a fashion that is not allowed).
However, one could argue that GPL contamination is too negative wording, as it only refers to the fact that if you use a GPL work beyond what is expressly allowed in the license, you are in breach of contract and could be held liable - but in this situation, you may instead license your work under the GPL and accept to be "contaminated".

## GPL Main Points

In the following paragraph, I try to summarize how the FSF (/the GNU Foundation) themselves interpret the GPL license. However, as I mention later in the section on [GPL Linking](#static-vs-dynamic-linking-gpl), most seem to argue that you can go further - for instance, to dynamically link against a GPL program, regardless how it is used, and still not be contamined (i.e. without being forced to release your work under the GPL or risk getting sued). However, the FSF disagrees.

To be sure that your work is not contaminated by the GPL, according to the FSF, the following should apply;
The work should be an aggregate (as per the GPL license), meaning that it is separate and independent from the GPL licensed program.
Therefore, the work should be able to function on its own, and any GPL components easily exchanged.
The FSF states, that _"you cannot incorporate GPL-covered software in a proprietary system"_ [2] and that a proprietary work cannot link to a GPL work (_"because the program actually links to the library [..] the terms of the GPL apply to the entire combination"_) [9].
On the other hand, they describe that it is allowed to use a plug-in with a larger work (one of which being covered by GPL) as long as they do not form a single combined program. Specifically, you are allowed to use fork and exec to run the plug-in. [1]
The term used is that both works should communicate "at arms length" [2].
At a minimum, the programs should run as separate processes and communicate over an IPC mechanism like pipes. They cannot directly share any data structures. [3]

The GPL does not apply if the project is only used privately or internally within a company, and not distributed to anyone else [4].

If you convey a work covered by GPL in a non-source format (e.g. as a binary), additional to the source code, you are also required to provide installation instructions.
These instructions could include makefiles and installation scripts, or whatever is necessary, to generate and (if applicable) run the executable.
This is required for GPL (v2, v3) and LGPL (v2.1 [5], v3), however, it is more explicitly stated in the later versions: GPLv3 and LGPLv3 [6].
For libraries covered by LGPL it is also required to enable the users to relink and run the libraries, as well as to provide instructions on how this can be done [7].
Comment, in the case that the work is only conveyed in source code, and not in any non-source format, you are not required to provide installation instructions as stated in the GPL licenses (also discussed here [8]).

Side note, LGPLv3 incorporates the full GPLv3 license and is therefore equivalent in many areas.


[1] - <https://www.gnu.org/licenses/gpl-faq.html#NFUseGPLPlugins>

[2] - <https://www.gnu.org/licenses/gpl-faq.html#GPLInProprietarySystem>

[3] - <https://www.gnu.org/licenses/gpl-faq.html#MereAggregation> (included below)

> "An “aggregate” consists of a number of separate programs, distributed together on the same CD-ROM or other media.
       The GPL permits you to create and distribute an aggregate, even when the licenses of the other software are nonfree or GPL-incompatible.
       The only condition is that you cannot release the aggregate under a license that prohibits users from exercising rights that each program's individual license would grant them.
>
>   Where's the line between two separate programs, and one program with two parts?
       This is a legal question, which ultimately judges will decide.
       We believe that a proper criterion depends both on the mechanism of communication (exec, pipes, rpc, function calls within a shared address space, etc.)
       and the semantics of the communication (what kinds of information are interchanged).
       If the modules are included in the same executable file, they are definitely combined in one program. If modules are designed to run linked together in a shared address space, that almost surely means combining them into one program.
>
> By contrast, pipes, sockets and command-line arguments are communication mechanisms normally used between two separate programs.
       So when they are used for communication, the modules normally are separate programs.
       But if the semantics of the communication are intimate enough, exchanging complex internal data structures,
       that too could be a basis to consider the two parts as combined into a larger program."

[4] - <https://www.gnu.org/licenses/gpl-faq.html#GPLRequireSourcePostedPublic>

[5] - <https://opensource.stackexchange.com/questions/4643/do-i-need-to-provide-build-install-instructions-for-lgpl-2-1-or-agpl-3-0-license>

[6] - <https://www.gnu.org/licenses/gpl-faq.html#InstInfo>

>   Specifically;
>
> LGPLv2.1: "an executable [..] must include any data and utility programs needed for reproducing the executable from it"
                     - <https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html>
>                     
>  GPLv3: "The “Corresponding Source” for a work in object code form means all the source code needed to generate, install,
                     and (for an executable work) run the object code and to modify the work, including scripts to control those activities."
                     - <https://www.gnu.org/licenses/gpl-3.0.html>

[7] - <https://www.qt.io/licensing/open-source-lgpl-obligations>

[8] - <https://opensource.stackexchange.com/questions/2688/do-you-violate-the-gpl-if-you-provide-source-code-that-cannot-be-compiled>

[9] - <https://www.gnu.org/licenses/gpl-faq.html#IfLibraryIsGPL>

_Additional discussion, not referred to in this article:_
> https://softwareengineering.stackexchange.com/questions/50118/avoid-gpl-violation-by-moving-library-out-of-process \
https://softwareengineering.stackexchange.com/questions/367844/can-i-include-a-gpl-v3-binary-with-my-proprietary-application-if-i-prompt-the-us/367850#367850 \
https://softwareengineering.stackexchange.com/questions/102778/is-running-an-executable-as-a-child-process-the-same-as-linking-a-library \
https://opensource.stackexchange.com/questions/5447/to-which-extent-gpl-license-contaminates-my-project



## (L)GPLv2 vs (L)GPLv3

GPLv3 and LGPLv3 are generally stricter than GPLv2 and LGPLv2.1, respectively.

The main differences between the versions are the following;

1. The added tivoization clause states that if you distribute user products (i.e. actual hardware products), you need to allow modification of the work covered under (L)GPLv3 on these devices [1,2]. That is, the manufacturer is not allowed to restrict modification of (L)GPLv3 software running on their products, as otherwise often done with different DRM mechanisms [5,7].
2. Unlike the predecessors, (L)GPLv3 provides an explicit clause that work distributed in a non-source format need to include installation instructions together with the source code. This is assumably stronger than LGPLv2.1 and GPLv2, which had a similar but much shorter mention of this. Although, I am not sure what this means in practice.
3. Similarly with patents - (L)GPLv3 provides an explicit patent clause¹ [4], also described in [1,4,5]. While GPLv2 and LGPLv2.1 only give an "implicit patent license" [5].
As a result of this, the Apache license should be compatible with GPLv3 (while incompatible with GPLv2) [6], but more on this later.²


In general, the (L)GPLv3 license was also internationalized, avoiding US-specific terminology [5,8].

For more information; the changes are briefly discussed here [5, 7], and in more detail here [8].

¹ _Together with the explicit mention of patents, so called patent retaliation is also included in GPLv3 [9] [10]._

² **_For more information on software patents, including for GPLv3, see my later post [Patents and open-source Software](https://r0x.se/#patents-and-open-source-software)._**

[1] - <https://www.qt.io/licensing/open-source-lgpl-obligations>

[2] - <https://www.gnu.org/licenses/gpl-faq.html#Tivoization> (included below)

>  "When people distribute User Products that include software under GPLv3, section 6 requires that they provide you with information necessary to modify that software.
       User Products is a term specially defined in the license; examples of User Products include portable music players, digital video recorders, and home security systems."
       
       
[3] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

[4] - <https://fsfe.org/activities/gplv3/patents-and-gplv3.en.html>

[5] - <https://www.ifross.org/en/what-difference-between-gplv2-and-gplv3>

[6] - <https://www.gnu.org/licenses/license-compatibility.html>, <https://www.apache.org/licenses/GPL-compatibility.html>, <https://opensource.stackexchange.com/questions/11082/why-is-the-gnu-gpl-v3-compatible-with-the-apache-license-v2-0>
      
[7] - <https://www.gnu.org/licenses/rms-why-gplv3.html>

[8] - <https://web.archive.org/web/20181223234838/https://www.ipa.go.jp/files/000028295.pdf> (Eben Moglen, GPL3: Process and Product, 21 December 2007)

[9] - <https://fsfe.org/activities/gplv3/patents-and-gplv3.en.html#Compatibility-with-broader-retaliation>

[10] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

## How is LGPL Weaker than GPL?

Your work gets contaminated by LGPL if it is "based on the library", e.g., if your work directly includes LGPL code or if your work cannot function without the LGPL parts (either on its own or by replacing the LGPL work).
However, the LGPL is referred to as weak copyleft since much can be accomplished while "combined" with non-copyleft code, which then falls under "works that use the library". [1]

In this latter case, your work is not contaminated even if you link against an LGPL licensed library. The following applies;
You may dynamically link against LGPL licensed libraries without disclosing your work. However, if you provide the LGPL library (dynamically linked), you need to provide its source.
On the other hand, if you statically link, you also need to provide information to enable users to relink the software. This might, for instance, be the object files of your work. [2] Statically linking can easier be seen as "based on the library", and it is therefore safer to dynamically link when possible [3].

 
Comment; Instead of licensing your work under the LGPL, it is also technically possible to license under the GPL while explicitly allowing linking (i.e. a _GPL linking exception_) [4]. An example of this is the so-called _Classpath exception_, as used in the GNU Classpath Java library [5].
However, by choosing GPL with the Classpath exception in favor of LGPL, you are forgoing the few requirements (described just above) that other works linking against your work have.

[1] - <https://copyleft.org/guide/comprehensive-gpl-guidech11.html>

[2] - <https://www.gnu.org/licenses/gpl-faq.en.html#LGPLStaticVsDynamic> (included below)

>  "(1) If you statically link against an LGPLed library, you must also provide your application in an object (not necessarily source) format,
              so that a user has the opportunity to modify the library and relink the application.
>              
>  (2) If you dynamically link against an LGPLed library already present on the user's computer, you need not convey the library's source.
              On the other hand, if you yourself convey the executable LGPLed library along with your application, whether linked with statically or dynamically,
              you must also convey the library's sources, in one of the ways for which the LGPL provides."
              
[3] - <https://www.qt.io/licensing/open-source-lgpl-obligations>

[4] - <https://en.wikipedia.org/wiki/GPL_linking_exception>

[5] - <https://resources.whitesourcesoftware.com/blog-whitesource/top-9-gpl-with-the-classpath-exception-questions-answered>


## Static vs. Dynamic Linking (GPL)

In this section I use the term GPL for referring to both GPLv2 and GPLv3, as they should be similar when it comes to linking.

To summarize; From a legal perspective, it is safer to use dynamic linking over static linking, as the risk of contamination is lower.¹ Dynamic linking is generally considered to be within the law according to legal experts, or at least, it should be allowed if it can be shown that the program in-fact functions and provides value even without the GPL work. Still, it is impossible to say conclusively without considering specific jurisdictions and recent cases regarding GPL compliance.

FSF describes that it is not in any way allowed for a proprietary program to directly link (dynamically or statically) to a program licensed under GPL [1] (as described earlier, they need to communicate "at arms length").
However, it has been claimed that it is acceptable to dynamically link to GPL code. Especially if the proprietary work is separate from the GPL work and does not depend on it.
Ergo, the proprietary work should be able to utilize components other than the GPL-affected ones and still function (additionally, it should not be a derivative work of the GPL project). [2,4]
Indeed, this is contrary to what FSF writes [1]. However, just because the FSF argues that the GPL should cover dynamic linking, does not necessarily make it so in practise [4]. From what I have read, dynamically linking GPL code is most often interpreted as to be allowed in US [2,6], English [4], and EU [3,5] law. While statically linking is often seen as not allowed or uncertain. Statically linking should be the same as including the code directly [4].




This was also discussed in an LWN article, regarding a presentation by Armijn Hemel, which states; _"The key point is that the build-time and run-time environments may be different [...].
 This is important because, in his opinion, dynamic linking moves questions about derivative works and the application of the GPL license into run time, because it is only at run time that libraries are linked with a program.
 The dynamically linked libraries that are used at run time could indeed be different—and have different licenses—from the libraries that were specified during the static linking phase.
 This implies that (depending who you ask) declaring the wrong dependencies in a binary could trigger license compliance issues."_ [3]

For additional reading, I refer to [Practical GPL[v2] Compliance](https://www.linuxfoundation.org/resources/publications/practical-gpl-compliance) and [GPL - the Linking Debate](https://web.archive.org/web/20130514013222/https://moorcrofts.com/documents/GPL%20-%20the%20Linking%20Debate.pdf).

Additional reading for another perspective, _"In short, the debate over static and dynamic linking simply misses the mark"_ [6].

¹ _Dynamic linking is always safer than static linking, regardless if the license is (L)GPLv2 or v3._

[1] - <https://www.gnu.org/licenses/gpl-faq.html#IfLibraryIsGPL> (included below)

> "Yes, because the program actually links to the library. As such, the terms of the GPL apply to the entire combination.
       The software modules that link with the library may be under various GPL compatible licenses, but the work as a whole must be licensed under the GPL"

[2] - <http://mediatechlaw.mstreetlegal.com/2014/04/25/open-source-dynamic-linking-and-licensing-consideration-for-developers/> (GPLv3, US law)

[3] - <https://lwn.net/Articles/548216/> (EU law?)

[4] - <https://web.archive.org/web/20130514013222/https://moorcrofts.com/documents/GPL%20-%20the%20Linking%20Debate.pdf> (GPLV2, English law)

[5] - <https://www.linuxfoundation.org/resources/publications/practical-gpl-compliance> (GPLv2, EU law?)

[6] - <https://web.archive.org/web/20110514024547/https://www.law.washington.edu/lta/swp/law/derivative.html/> (GPLv2, US law)

[7] - <https://www.qt.io/licensing/open-source-lgpl-obligations> (LGPLv3)

## What is License Compatibility?

In general, license compatibility refers to the fact that you can combine multiple programs of different licenses (which you do not hold the copyright for) as long as you adhere to the licenses.
For instance, you may take a BSD and an MIT licensed program and combine them into one proprietary program.
You may then release this work under a proprietary license and impose any additional restrictions.
However, you must still fulfill all the requirements of the licenses, which in this example requires the inclusion of both original copyright notices.
Far from every license is compatible, as each obligation in the licenses must be fully followed. [p. 161, 1]

GPLv3 (and a similar clause in GPLv2) states that _"you may not impose any further restrictions on the exercise of the rights granted or affirmed"_, which limits its compatibility with other licenses.
Therefore, one needs to be careful when claiming a license is compatible with GPL, possibly even if the license is listed as compatible by the FSF [p. 160, 1].
It is due to this clause, that GPLv3 code cannot be included in Apache projects, while the opposite (i.e. Apache code in GPLv3 projects) is allowed [4].

Comment; GPLv2 and GPLv3 are not compatible. However, as it should be explicitly stated that _"GPL version 2 or any later version"_ can be used, the user or developer can decide which version to follow. As far as I understand, this has nothing to do with license compatibility but rather a type of multi-licensing.

#### License Compatibility - Example of Use:

First, if there are multiple contributors (i.e. copyright holders) to a project, _all_ must agree if you are to change license (e.g., by signing a CLA beforehand).
However, there is an exception. Namely, you are always allowed to switch to a compatible license [2]¹.
Of course, the old license still applies to the software at that earlier point.

Second, when multiple compatible projects are merged, all licenses still apply to their respective parts.
However, if you wish, the combined program can be seen as licensed under only the most stringent license present - assuming they are compatible.
For instance, GPLv3 and Apache 2.0 are compatible (in one direction [4]), and together a combined work under these licenses could be seen as the strong copyleft GPLv3 [3].

¹ _Details regarding compatible licenses are described here [3]._

[1] - Andrew M. ST. Laurent (2004), Understanding Open Source and Free Software Licensing, ISBN 978-0596005818

[2] - <https://opensource.stackexchange.com/questions/33/how-can-a-project-be-relicensed/46#46>

[3] - <https://www.gnu.org/licenses/license-compatibility.html>

[4] - <https://www.apache.org/licenses/GPL-compatibility.html> (included below)
>  "Apache 2 software can therefore be included in GPLv3 projects, because the GPLv3 license accepts our software into GPLv3 works.
>  However, GPLv3 software cannot be included in Apache projects.
>  The licenses are incompatible in one direction only,
>  and it is a result of ASF's licensing philosophy and the GPLv3 authors' interpretation of copyright law."
