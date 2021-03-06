
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

In the following paragraph, I try to summarize how the GNU Foundation themselves interpret the GPL license. However, as I mention later in the section on [GPL Linking](#static-vs-dynamic-linking-gpl), some argue that you can go further - e.g. to (in certain cases) dynamically link against a GPL program - and still not be contamined (i.e. without being forced to release your work under the GPL or risk getting sued).

So to be sure that your work is not contaminated by the GPL, the following should apply;
The work should be an aggregate (as per GPL license), meaning that it is separate and independent from the GPL licensed program. Therefore, the work should be able to function on its own, and any GPL components easily exchanged.
For instance, it is allowed to use a GPL-covered plug-in as long as it DOES NOT form a single combined program with the work. So, you are allowed to use fork and exec to run the external GPL binary. [1]
The term used is that both works should communicate "at arms length" [2]. At a minimum, the programs should run as separate processes and communicate over an IPC mechanism like pipes. They cannot directly share any data structures. [3]

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

> Additional discussion\
https://softwareengineering.stackexchange.com/questions/50118/avoid-gpl-violation-by-moving-library-out-of-process \
https://softwareengineering.stackexchange.com/questions/367844/can-i-include-a-gpl-v3-binary-with-my-proprietary-application-if-i-prompt-the-us/367850#367850 \
https://softwareengineering.stackexchange.com/questions/102778/is-running-an-executable-as-a-child-process-the-same-as-linking-a-library \
https://opensource.stackexchange.com/questions/5447/to-which-extent-gpl-license-contaminates-my-project



## (L)GPLv2 vs (L)GPLv3

GPLv3 and LGPLv3 are generally stricter than GPLv2 and LGPLv2.1, respectively.

1. The tivoization clause states that if you distribute user products (i.e. actual hardware products), you need to allow modification of the work covered under (L)GPLv3 on these devices [1,2].
2. Unlike their predecessors, (L)GPLv3 provides an explicit clause that work distributed in a non-source format need to include installation instructions together with the source code. This is assumably stronger than LGPLv2.1 and GPLv2, which had a similar but much shorter mention of this. Although, I am not sure what this means in practice.
3. Similar with patents - (L)GPLv3 provide an explicit patent clause [4], also described in [1,4,5]. While GPLv2 and LGPLv2.1 only give an "implicit patent license" [5].
As a result of this, as I understand, the Apache license is incompatible with GPLv2 but is compatible with GPLv3 [6].

Read more here [5, 7], and the changes more in detail [8].



[1] - <https://www.qt.io/licensing/open-source-lgpl-obligations>

[2] - <https://www.gnu.org/licenses/gpl-faq.html#Tivoization> (included below)

>  "When people distribute User Products that include software under GPLv3, section 6 requires that they provide you with information necessary to modify that software.
       User Products is a term specially defined in the license; examples of User Products include portable music players, digital video recorders, and home security systems."
       
       
[3] - <https://www.gnu.org/licenses/gpl-faq.html#v3PatentRetaliation>

[4] - <https://fsfe.org/activities/gplv3/patents-and-gplv3.en.html>

[5] - <https://www.ifross.org/en/what-difference-between-gplv2-and-gplv3>

[6] - <https://www.gnu.org/licenses/license-compatibility.html>, <https://www.apache.org/licenses/GPL-compatibility.html>, <https://opensource.stackexchange.com/questions/11082/why-is-the-gnu-gpl-v3-compatible-with-the-apache-license-v2-0>
      
[7] - <https://www.gnu.org/licenses/rms-why-gplv3.html>

[8] - <https://www.ipa.go.jp/files/000028295.pdf> (Eben Moglen, GPL3: Process and Product, 21 December 2007)

## How is LGPL Weaker than GPL?

Your work gets contaminated by LGPL if it is "based on the library", e.g., if your work directly includes LGPL code or if your work cannot function without the LGPL parts (either on its own or by replacing the LGPL work).
However, the LGPL is referred to as weak copyleft since much can be accomplished while "combined" with non-copyleft code, which then falls under "works that use the library". [1]

In this latter case, your work is not contaminated even if you link against an LGPL licensed library. Although, the following applies;
You may dynamically link against LGPL licensed libraries without disclosing your work. However, if you provide the LGPL library (dynamically linked), you also need to provide its source.
On the other hand, if you statically link, you need to provide information to enable users to relink the software. This might, for instance, be the object files of your work. [2]
Statically linking can easier be seen as "based on the library", and it could therefore be safer to dynamically link when possible (or relicense under LGPL) [3].
 
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

From a legal perspective, it is generally safer to use dynamic over static linking, which means that the risk of contamination is also lower.

FSF describes that it is not in any way allowed for a proprietary program to directly link to a program licensed under GPL [1] (as described earlier, they need to communicate "at arms length").
However, it has been claimed that (in some jurisdictions) it is acceptable to dynamically link to GPL code, assuming that the proprietary work is separate from the GPL work and does not depend on it.
Ergo, the proprietary work should be able to utilize components other than the GPL-affected ones and still function (additionally, it should not be derivative work of the GPL project). [2]
There seems to be no simple answer for this question, as these statements seem contradictory to what FSF writes [1], proceed with caution.

This was also discussed in an LWN article, which states; _"The key point is that the build-time and run-time environments may be different [...].
 This is important because, in his opinion, dynamic linking moves questions about derivative works and the application of the GPL license into run time, because it is only at run time that libraries are linked with a program.
 The dynamically linked libraries that are used at run time could indeed be different—and have different licenses—from the libraries that were specified during the static linking phase.
 This implies that (depending who you ask) declaring the wrong dependencies in a binary could trigger license compliance issues."_ [3]


[1] - <https://www.gnu.org/licenses/gpl-faq.html#IfLibraryIsGPL> (included below)

> "Yes, because the program actually links to the library. As such, the terms of the GPL apply to the entire combination.
       The software modules that link with the library may be under various GPL compatible licenses, but the work as a whole must be licensed under the GPL"

[2] - <http://mediatechlaw.mstreetlegal.com/2014/04/25/open-source-dynamic-linking-and-licensing-consideration-for-developers/>

[3] - <https://lwn.net/Articles/548216/>


## What is License Compatibility?

In general, license compatibility refers to the fact that you can combine multiple programs of different licenses (which you do not hold the copyright for) as long as you adhere to the license.
For instance, you may take a BSD and an MIT licensed program and combine them into one proprietary program.
You may then release this work under a proprietary license and impose any additional restrictions.
However, you must still fulfill all the requirements of the licenses, which in this example at least requires the inclusion of the original copyright notices.
Far from every license is compatible, as each obligation in the licenses must be fully followed. [p. 161, 1]

GPLv3 (and a similar clause in GPLv2) states that _"you may not impose any further restrictions on the exercise of the rights granted or affirmed"_, which limits its compatibility with other licenses.
Therefore, one needs to be careful when claiming a license is compatible with GPL, possibly even if the license is listed as compatible by the FSF [p. 160, 1].

#### License Compatibility - Example of Use:

First, if there are multiple contributors (copyright holders) to a project _all_ must agree if you are to change license (e.g., by signing a CLA beforehand).
However, there is an exception. Namely, you are always allowed to switch to a compatible license [2] (details are described here: [3]).
Of course, the old license still applies to the software at that earlier point.

Second, when multiple compatible projects are merged, all licenses still apply to their respective parts.
However, if you wish, the combined program can be _seen_ as licensed under the most stringent license present - assuming they are compatible.
For instance, GPLv3 and Apache 2.0 are compatible, and together a combined work under these licenses could be seen as the strong copyleft GPLv3 [3].


[1] - Andrew M. ST. Laurent (2004), Understanding Open Source and Free Software Licensing, ISBN 978-0596005818

[2] - <https://opensource.stackexchange.com/questions/33/how-can-a-project-be-relicensed/46#46>

[3] - <https://www.gnu.org/licenses/license-compatibility.html>

