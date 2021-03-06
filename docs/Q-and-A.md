# Q&A about Sidetree
**The questions are mixed basic and detailed, the answers are mostly directed towards generally interested people and newbies.**

Why should you read or step through the Q&A? To get a different angle to the same topic: Sidetree.

<img src="./images/sidetree-logo.png" alt="Sidetree logo" border="0" width="150">

This document relies on a [Glossary](./Glossary.md) file that has:
- a alphabethically ordered list of **abbreviations**
- a alphabethically ordered list of **definitions**
Terminology specific for Sidetree can be found [here](https://identity.foundation/sidetree/spec/#terminology). The following definitions are specificly listed to support the *Question and Answers* below on a simpler level, and to be able to put Sidetree in relation to other fields of interest.

**The questions are of a varied level: basic and detailed. The answers are mostly directed towards generally interested people and newbies.**\
*Q = one star question. Novice to `Sidetree`, advanced in DIDs\
**Q = two star question. Proficient in DIDs and advanced in `Sidetree`\
***Q = three star question. Expert in DIDs and proficient in `Sidetree`

```
{TBW} means: to be written
```
- [Q&A about Sidetree](#qa-about-sidetree)
    + [Disclaimer](#disclaimer)
    + [List of abbreviations and definitions](#list-of-abbreviations-and-definitions)
  * [Knowledge you should be confidently applying](#knowledge-you-should-be-confidently-applying)
  * [Actions you should be comfortable with](#actions-you-should-be-comfortable-with)
- [Jump table to categories](#jump-table-to-categories)

Inspired by [specifications](https://identity.foundation/sidetree/spec/) and questions raised during DIF Sidetree WG meetings, but also issues created and handled [here](https://github.com/decentralized-identity/sidetree/issues) and the progress made, here on Github (Turn on 'Watch' if you want to be notified of conversations).

Beware: A Q&A is always *work in progress*. Tips & help welcome.

### Disclaimer
None of the respondents in the **open** repo and presentations have been explicitly named as a source, except for ***@csuwildcat*** (Daniel Buchner, expert), ***@thehenrytsai*** (Henry Tsai, expert) and ***@henkvancann*** (documentation). 

If there is no reference added to the answers, then its content stems from either one or more of these sources
- [Specifications]https://identity.foundation/sidetree/spec/
- [Github Sidetree](https://github.com/decentralized-identity/sidetree)
- [What bitcoin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)
- it's Daniel Buchner or Henry Tsai who answered the question. 
Most of the editing is done by @henkvancann, which might have introduced ommission, errors, language glitches and such. Sorry for that, feel free to correct by submitting a pull request (PR).\
For practical reasons educational images uploaded by Github members may have been downloaded. We de-personalised them by giving images a new name. Under these new names these images have been uploaded to github and used in the Q&A to clarify the questions and answers.

Sidetree's content is licensed under the [Apache License 2.0](https://github.com/decentralized-identity/sidetree/blob/master/LICENSE). 

We've done our best to protect the privacy of the Github by investigating the images we used. We haven't come across personal identifiable information (pii). However, should we have made a mistake after all, please let us know and we'll correct this immediately.

### List of abbreviations and definitions
- [Abbreviations](./Glossary.md#Abbreviations)

- [Definitions:](./Glossary.md#definitions)
      - [Agent](./Glossary.md#agent)
      - [Agency](./Glossary.md#agency)
      - [Bidirectional model transformation](./Glossary.md#bidirectional-model-transformation)
      - [Claim](./Glossary.md#claim)
      - [Content-addressable hash](./Glossary.md#content-addressable-hash)
      - [Controller](./Glossary.md#controller)
      - [Cryptocurrency](./Glossary.md#cryptocurrency)
      - [Decentralized Identity](./Glossary.md#decentralized-identity)
      - [Delta-based](./Glossary.md#delta-based)
      - [Deterministic Ruleset (of Sidetree)](./Glossary.md#deterministic-ruleset--of-sidetree)
      - [Entropy](./Glossary.md#entropy)
      - [Entity](./Glossary.md#entity)
      - [Identity](./Glossary.md#identity)
      - [JSON Web Key](./Glossary.md#json-web-key)
      - [Key](./Glossary.md#key)
      - [Merkle tree](./Glossary.md#merkle-tree)
      - [Normative](./Glossary.md#normative)
      - [Non-normative](./Glossary.md#non-normative)
      - [Payload](./Glossary.md#payload)
      - [Public Key Infrastructure](./Glossary.md#public-key-infrastructure)
      - [Race condition](./Glossary.md#race-condition)
      - [Root of trust](./Glossary.md#root-of-trust)
      - [Secret](./Glossary.md#secret)
      - [Self Sovereign Identity](./Glossary.md#self-sovereign-identity)
      - [Subject](./Glossary.md#subject)
      - [Transfer](./Glossary.md#transfer)
      - [Transferable identifier](./Glossary.md#transferable-identifier)
      - [Validator](./Glossary.md#validator)
      - [Verifiable Credential](./Glossary.md#verifiable-credential)
      - [W3C DID](./Glossary.md#w3c-did)
      - [WebAssembly](./Glossary.md#webassembly)
      - [(Digital Identity) Wallet](./Glossary.md#-digital-identity--wallet)

## Knowledge you should be confidently applying
- The definitions above
- W3C DIDs
- Public private key pairs
- hierarchical deterministic derivation paths
- Base58
- IPFS

## Actions you should be comfortable with
- Amend knowledge and keep existing knowledge up to date
- create a key pair safely and back it up safely

# Jump table to categories
- [General](#qa-section-general)
- [Sidetree operational](#qa-section-sidetree-operational)
- [Userinterface](#qa-section-userinterface)
- [Identifiers](#qa-section-identifiers)
- [Wallets](#qa-section-wallets)
- [Signatures](#qa-section-signatures)
- [Private Key Management](#qa-section-private-key-management)
- [Blockchain](#qa-section-blockchain)
- [Agencies](#qa-section-key-agencies)
- [ION](#qa-section-ION)

# Q&A section General

## *Q: What is Sidetree?
Sidetree is a protocol for creating a scalable decentralized public key infrastructure ([DPKI](./Glossary.md#public-key-infrastructure)) networks that can run atop of any existing decentralized ledger system (e.g. Bitcoin) and be as open, public, and permissionless as the underlying ledger they utilize.

#### **Q: Why only a protocol, why scalable, why decentralized, why a ledger, why permissionless, why open and public?
1. Sidetree is a _protocol_ because we need it to be multi applicable. Implementers will be provided with software tools and toolkits and the protocol has both `normative` and non-normative guidelines.
2. The _scalability_ feature is needed because of the astronomical numbers that are associated with digital identifiers, the numerous life events of each identifier and the mulitple use of each individual identifier. Every individual, group or thing on earth can have multiple identifiers associated with them.
3. Privacy and guarding control over are the main drivers for the deer wish to _decentralize_ identifiers. If you don’t like being tracked and you don’t like anybody else controlling your identity, decentralization is the way to go. 
4. A single global ledger is not needed for a Sidetree implementation. Some sidetree implementations do make the choice to use one global ledger (e.g., did:ion), while other Sidetree implementations make more ad-hoc choices (e.g., did:orb).
5. Permissioned identifiers are limited to a certain domain of application. Sidetree does not want to confine itself and will be as _permissionless_ as the underlaying ledger.
6. Lastly Sidetree needs to be open and public and at the same the protocol and its applications need to hide and protect all sensitive identity related data. This seems to contradict each other. However in Sidetree it is doable. Cryptography and the protocol safeguard privacy and the _open public_ characteristic offers availability and inclusion at the same time.
(_@henkvancann_)

## **Q: What is the setting of sidetree?
The protocol allows users to create _globally unique, user-controlled identifiers_ and manage their associated metadata, all _without the need for centralized authorities_ or trusted third parties. The syntax of the identifier and accompanying data model used by the protocol is conformant to that defined by W3C Decentralized Identifiers. Implementations of the protocol can be codified as their own distinct DID Methods and registered in the W3C DID Method Registry.

## *Q: What is in the name 'Sidetree'?
The name “Sidetree” combines two hints as to its technical inspirations and superpowers. Each Sidetree network functions as a kind of identity-specific “sidechain” periodically pinned to an underlying chain in much the same way that so-called “Layer 2 Networks”.  These include the Lightning network running atop Bitcoin.\
(_@bumblefudge_)

## **Q: How is the inner working of Sidetree?
<img src="../www/diagrams/architecture.png" alt="Architecture of Sidetree" border="0" width="400">

#### ***Q: Why have the concept of index files?
It would be ideal to be able to fetch metadata about the batched operations efficiently, without needing to download the entire batched operation. This design is needed for the implementation of "light nodes".

## *Q: What are the main components of a sidetree system?
The figure below illustrates the three primary components of a Sidetree-based DID system:
1. Single point of definition
2. Safe-guarded recording of events
3. Access to (proofs of) stored data with a time stamp
<img src="./images/sidetree-system.png" alt="System components of Sidetree" border="0" width="400">

#### **Q What exactly does a "system" mean in Sidetree?
It is a DID overlay network. 
- The underlying anchoring system that serves as the anchoring and linear sequencing system for DID operations.
- The Sidetree nodes themselves, which interact with the anchoring system to anchor operations, fetch and replicate data from the CAS network, and process operations in accordance with the protocol deterministic ruleset.
- An integrated Content-Addressable Storage (CAS) network layer Sidetree nodes use to distribute and replicate DID operation files.

<img src="./images/layers-of-SSI-interop.png" alt="Layers of SSI interopability" border="0" width="600"> 

## Who is Sidetree for?
Any team or organisation that wants to create an DID based on Sidetree, because of its typical Layer 2 properties, not bloating any Layer 1 solution. Laying a foundation for layer 3 development, in the DID to be developed, that will result in W3C DID compliant VCs.
_(@henkvancann)_

## Why should we care about Sidetree or Self Sovereign Identity
We don't have any native identity today. You can't really have a verified presence in the world. Like if you're getting scammers impersonating you all the time on social media channels, it's really hard. You deserve to have that presence in the digital world, just like you are a person in the real world. 

Even your Twitter handle, for instance, as we know is **certainly leased** to you. These are identifiers that _can be taken from you_ at any time for any number of reasons, whether it be a social provider who doesn't like what you wrote and you're suspended or it's removed or maybe a company just goes out of business.

If you assert your identity and it's backed by strong cryptography, someone browsing an application on the web could validate it themselves. I think that's what we really want to empower people to do, is remove this pressure point from gatekeepers because a lot of them are not even incentivized to care.

We're moving everything to a digital world, just like we don't have paper mail, we have email now. When those things happen, proofs like, 'do you own your car?' or 'the deed to your house', all that kind of stuff, when that starts getting digitized and tied to some identifier, it really better be an identifier that can't be taken from you at a whim, by either a company or some bad actor because that would be pretty scary.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## **Q:  Why use Sidetree?
It is a DIDComm layer (2); which is layer 1 agnostic and uses Layer 1 very efficiently. Sidetree does not require trusted intermediaries, centralized authorities, special protocol tokens, or secondary consensus mechanisms, while preserving the core attributes of decentralization and immutability of the underlying ledger systems it is implemented on.
_(@henkvancann)_

## **Q: What is so unique to Sidetree?
Compared to other architectures in the space Sidetree is:
1. Massive parallel processing power
2. Strongly intrinsically consistent
3. Users of identity system based on Sidetree control their own history

Sidetree uniquely provides a Content Adressable structure for distributed systems.

Current approaches that utilize these ledger systems to create decentralized identifier networks suffer from severely limited transactional volumes and other performance issues. Sidetree is a ‘Layer 2’ protocol that runs atop decentralized anchoring systems.\
Sidetree has a very small footprint on anchoring - or settlement - Layers ("Layer 1"). It stashes multiple layer 2 identity transactions into one layer 1 transaction; it's "Lightning-Network-like" in Bitcoin. Within DIF we call this the (Public) Trust Layer.\
_(@henkvancann)_

##  *Q: Is Sidetree a DID?
`Sidetree` is not a `DID` method. The related `DID` method is [`did:core`](https://www.w3.org/TR/did-core/) Implementations of the protocol can be codified as their own distinct DID Methods and registered in the W3C DID Method Registry; e.g. [`did:ion`]().\
_(@henkvancann)_
#### **Q: How does Sidetree technically relate to DID methods?
Sidetree-based DID Method implementations are overlay networks composed of independent peer nodes (Sidetree nodes) that interact with an underlying decentralized anchoring system to write, observe, and process replicated DID PKI state operations using deterministic protocol rules that produce an eventually strongly consistent view of all DIDs in the network.\
[More at source](https://identity.foundation/sidetree/spec/#introduction)

#### **Q: What is the functional relationship between Sidetee and DIDs?
Decentralized identifiers (DIDs) enable a person or entity to securely and directly “anchor” their data-sharing activities to a shared ledger securely by cryptography. The first generation of DID systems accomplished this with a 1-to-1 relationship between “blockchain addresses” (cryptographic identities) and the more flexible, powerful addresses called DIDs. These latter functioned as privacy-preserving extensions of the blockchain addresses to which they were closely coupled. In this way, each DID effortlessly inherited the formidable security guarantees of those blockchains-- but in many cases, they also inherited scalability problems and economic models that were a bad fit for many DID use-cases.\
Sidetree is a systematic, carefully-engineered protocol that loosens that coupling between blockchain anchor-points and DID networks anchored to them, replacing a 1-to-1 relationship with a 1-to-many relationship. Depending on the use-case and implementation strategies chosen, the protocol can optimize for scalable performance, for developer-friendly ergonomics and software development kits (SDK), for the portability of DIDs and networks of DIDs across multiple anchoring systems, and even for high availability in contexts where a global blockchain cannot be relied upon directly.\
(_@bumblefudge_)

##  **Q: How does Sidetree match the `trust-over-ip` model and in the `W3C DID standardization`?
The DIF interoperability model looks like this:
<img src="./images/layers-of-SSI-interop.png" alt="Layers of SSI interopability" border="0" width="600"> 
Another relevant piece to consider as soon as comparisons with third party models come up, is the
[DIF Cross Community Architecture Survey](https://github.com/decentralized-identity/decentralized-identity.github.io/blob/master/assets/crosscommunity-architecture-survey-oct-2020.pdf)

Comparison to the Trust over IP Foundation model:
- Sidetree's goal is to offer a scalable decentralized public key infrastructure
- Layer 1 (settlement layer): blockchain agnostic and databases to register identities and settle 'transactions' between between, `DDO`s, and `VC`s, Sidetree implementations use bitcoin and ethereum in 2021.
- Layer 2 (communication layer): Examples are DID:ION and DID:ORB.
- Layer 3 (transaction layer): {TBW prio 2}
- Layer 4 (application layer): {TBW prio 3}
_(@henkvancann)_

##  *Q: Who is Sidetree? Is it a company or a not for profit?
Sidetree sits under the *Decentralized Identity Foundation*, [DIF](https://identity.foundation), and within that Sidetree is in the Sidetree WG of DIF.
Due to its licensing structure, Sidetree isn't owned by anyone and everyone at the same time. The Intellectual Property Right of Sidetree is hosted with `DIF`. It is an open source project.

On github Sidetree is - and will become even more - a thickening bunch of repositories:
 -  https://github.com/decentralized-identity/Sidetree 

 Lastly, Microsoft is an important promotor of Sidetree and employer of some contributors.
 _(@henkvancann)_

 ##  *Q: Why is a company like Microsoft working on decentralized IDs using Bitcoin? 
_What are the feelings with Bitcoin around Microsoft? Is there a general kind of acceptance and like about it?_

Not everyone is into Bitcoin, I would say the majority aren't. They don't care, they're product people, they want to get something done. They do understand that there's one system out there that's just stood and just embattled the test of time. So that part is like sort of empirical; you can't really argue with that part. There are believers among the people who do believe in Bitcoin.

But I'd say the majority, they believe in decentralizing. The reason they believe in it, is for all the things it does, not necessarily how we're doing it, but what it does. What it does for people, what it enables for the business, and so on. I personally believe Sidetree needs to be censorship resistant and tamper-evasive as possible. So that's the reason why I heavily encouraged Microsoft to go this route. But it becomes a humanitarian thing and it's hard to argue with.

The alternative is you could go set up some private permission blockchain or something, but that's only as decentralized as whoever is running those few nodes that gets to decide everything. That's not really something we're interested in, because it's not significantly differentiated from the centralized identity systems we provide today. It's just not something that might be good for people; to get people involved in a system where they could be shut off.

##  *Q: In what programming languages is Sidetree available?
There are two JavaScript implementations that I know about. The reference implementation hosted at DIF and also https://github.com/transmute-industries/sidetree.js. Sidetree has also been implemented in Go: https://github.com/trustbloc/sidetree-core-go. 
_(@troyronda)_

##  *Q: Does Sidetree cooperate with other projects in the self-sovereign Identity field?
Yes, Sidetree sits under the *Decentralized Identity Foundation*, [DIF](https://identity.foundation), and is part of the *Identity and Discovery* Workgroup. {TBW prio 3: There are also non-formal relation with the newly launched trust-over-ip foundation?}

##  *Q: Why is Microsoft so interested in supporting these developments?
_What's the value to Microsoft in working on this?_

There's a lot of things you just can't do with an identity safely unless people own their own IDs. So they can't find moneyed special deals with say just LinkedIn or just any email provider, or something like that, that might have a specific integration. It actually unlocks the ability to do a lot of different things, like do digital diplomas at scale, to do credentialing for skills and stuff like that, at scale.

In a way that's also standardized, like right now, it's just like people can issue these badges, there's different badge protocols. But it's pretty ad hoc, there's no real systemic way of find them and verify them and it's kind of a mess. So in order for us to unlock a ton of business opportunity in LinkedIn, in other investments we've made, things like GitHub and all these other things, you have to have users owning their own ID. It can't be a Microsoft-owned ID or it's just not safe to do these certain use cases.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## **Q: What's the diffrence between a `normative` and `non-normative` description or theory?
See the [definitions](#normative) section for what both are. For example, theories of ethics are generally `normative` - you should not kill, you should help that person, etc. Economics is most commonly `non-normative` - instead of asking “how should this person choose which goods to buy?”, we are often more interested in “how does this person choose which commodities they buy?”.

## **Q: Is Sidetree privacy preserving / GPDR proof?
These are the information-hiding measures taken in the protocol to facilitate compliance with privacy rules:
- No sensitive data on layer 1, which can be an open public blockchain
- THe content in the CAS layer 2, example IPFS, works with `commitments`. A commitment can be shared without revealing the commit value.
- Files-structures are designed to minimize permanently retained data
- Operation Request of type Recover or Deactivate
{TBW prio 2: unclear wether `Deactivate` obeys the right to be forgotten}\
_(@henkvancann)_

## **Q: Is there like a central, GitHub repository that someone or some group of people are responsible for?
_Could we contribute to the repository?_

it is in the Decentralized Identity Foundation's GitHub depository, [Sidetree](https://github.com/decentralized-identity/sidetree) is the name of it. So you can contribute code there, you can read every line of code. There's no code insertions after the fact, like every bit of every piece of code that we run, as an ION node, is there. So it's totally inspectable.
- [Contribution guidelines for the project](https://github.com/decentralized-identity/sidetree/blob/master/docs/contribution-guidlines.md).
- [The Sidetree release process](https://github.com/decentralized-identity/sidetree/blob/master/docs/release-process.md)
- [The Sidetree coding style guide](https://github.com/decentralized-identity/sidetree/blob/master/docs/styleguide.md)

# Q&A section Sidetree operational

## *Q:  Where can I download Sidetree?
On (sub)page(s of) [github](https://github.com/decentralized-identity/sidetree)

##  *Q: Where can we find the code and how could a coder get started?
The homepage on github [README.md](../README.md) pretty much sums up all the possibilities to download the available code and how developers can engage in the development process currently. We welcome contributions.

##  **Q: What are the external dependencies of Sidetree?
_I hear ya: "Sidetree is able to do all this **without requiring** trusted intermediaries, centralized authorities, special protocol tokens, or secondary consensus mechanisms, while preserving the core attributes of decentralization and immutability of the underlying ledger systems it is implemented on." But what does Sidetree require instead?_

Sidetree is dependent of:
1. A content addressable storage layer (e.g., IPFS)
2. Reasonable fees and confirmation-times on layer 1
3. Consensus, transaction validation and governance in general of the layer 1 blockchain it settles on.
4. Ongoing development and blockchain maintenance for safety of the records now and in the future.
5. {TBW prio 2}
_(@henkvancann)_

##  **Q: In what can we find the efficiency booster that Sidetree promises to be?
Sidetree nodes that participate in writing operations into the overlay network do so by **anchoring** Content-Addressable Storage (`CAS`) (e.g. IPFS) references to **aggregated** bundles of operations in an underlying ledger.

##  ***Q: "Process operations in accordance with the protocol deterministic ruleset." What does this mean?
Read this [section](https://identity.foundation/sidetree/spec/#late-publishing) that illustrates a DID owner, Alice, creating forks by creating and anchoring operations in the past that she does not expose to the network. Known as _Late Publishing_ of a DID operation.\
This type of processing guarantees only one `fork` of a DID’s state history can ever be valid.

##  *Q: What would you see as the main drawback of Sidetree?
There aren't many. Sidetree has Self-Certifying Identifiers, however they are non-transferable. {Right?}
_(@henkvancann)_

##  *Q: How can it be one solution, fit for more DIDs? 
DID Methods based on the Sidetree protocol all share the same identifier format. The unique identifier segment of a Sidetree-based DID, known as the DID Suffix, is derived by using the Hashing Process to generate a hash value from the canonicalized Create Operation Suffix Data Object. The DID Suffix is cryptographically bound to the initial PKI state of the DID, which means Sidetree DIDs are also self-certified.

## *Q: Where you would need something quite different than Sidetree to solve a similar problem?
In a private situation with no self sovereignty. A Certification Authority in combination with a federated setup could do, like it has done the past decades. But in that SSI become Self Service Identity at best, because the Identifiers are owned and controlled by a third party.
_(@henkvancann)_

## **Q: How does Sidetree scale
This image speaks a thousand words:\
<img src="./images/Sidetree-file-structure.png" alt="Sidetree file structure" border="0" width="500">
Sidetree is a lean and mean structure. The content of Sidetree mainly consists of JSON files of hashes, signatures and other cryptographical proofs and pointers. And it connects to other highly scaleable technologies, like IPFS and blockchains.\
<img src="./images/sidetree-logo.png" alt="Sidetree logo" border="0" width="100" align="right">
The importance of this structure for scaleability is rewarded in the Sidetree-logo.

## ***Q: How does Sidetree keep data internally consistent over nodes?
In brief: By using **delta-based** Conflict-Free Replicated Data Types. _(@henkvancann)_

Despite early availability on the market, `BX` tools did not gain much user appreciation because of semantic issues. A user should clearly understand the behavior of synchronization procedures implemented by a tool. The majority of algebraic BX frameworks are _state-based_. Synchronizing operations take the states of models before and after update as input, and produce new states of models as output. This design assumes that model alignment, i.e., discovering relations (deltas) between models,
is done by update propagating procedures themselves. Hence, two quite different operations—heuristics-based delta discovery and algebraic delta propagation are merged, which causes several theoretical and practical problems; See the source for several examples.\
To separate delta discovery and propagation, several researchers proposed to build `delta-based` frameworks, in which propagation operations use deltas as input and output rather than compute them internally. Such frameworks (a general one and a **tree-oriented**) have been built for the _asymmetric_ BX case, in which one model in the pair is a view of the other and hence does not contain any new information. In practice, however, it is often the case that two models share some information but each of them contains something new not present in the other; we call this case _symmetric_ `BX`.\
[Source and more info](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.386.7739&rep=rep1&type=pdf)

To summarize: Sidetree keeps data consitent by using a delta-based tree-oriented framework and performs _symmetric_-`BX`information sharing.\
_(@henkvancann)_

## **Q:  How does Sidetree keep identifiers secure?
 - Internally by commitment schemes
 - Externally by stressing the importance of proper key management

## **Q: How to handle multiple versions of Sidetree protocol. How to keep the network in sync?
The rules and parameters of the Sidetree protocol may change in the future, resulting in new versions of the specification. 
#### Version Segment Definitions:
1. Major: Major protocol evolution, with breaking protocol advancements so large they warrant incrementing the major version.
2. Minor: Critical updates, protocol forking changes, or security patches that require all nodes to upgrade.
3. Patch: Non-critical changes that do not require nodes to upgrade.

#### New Version Activation
New versions of the protocol, or modifications to parameter values by implementers, muat be activated at a specified _Ledger Time_ so **all nodes can remain in sync by enforcing the same ruleset and parameters** beginning at the same logical starting point.\ 
All transactions that occur after the specified Ledger Time will adhere to the associated version’s rules and parameters until a newer version of the protocol is defined and implemented at a future Ledger Time.\
New Version Activation is **necessary for Minor and Major version segments**; the ones with breaking protocol advancements, and protocol forking changes, or security patches.
_(@henkvancann)_

## Could Sidetree work with pruned or sharded blockchains?
No, any node needs a full copy of the blockchain that serves as a settlement layer 1. The reason is ordering of operation on DID is done via consensus of the blockchain.\
_(@henkvancann)_
## How to bootstrap Sidetree on the internet? Is it like fax machine; the more there are the more effective it is?
It's bootstrapped by the first DID method that uses Sidetree under the hood. The more use of those DIDs the more Sidetree gets used.  However, there is no network effect as such from extended use. None-the-less there is a huge network effect when mulitple DID methods are running on Sidetree, because they share the same resolution, protocol and file structure in the CAS.
_(@henkvancann)_

## What do I need to purchase to operate Sidetree or on sidetree based DIDs like ION?
To look up the IDs in ION, you have to have a full node, you've got to have the index of history. So in fact, we're going to be spawning a new reason why people will want to run full nodes, because it actually provides you concrete value you absolutely cannot get any other way. So running a node for us, it's a priority that anyone be able to do it.

So our target hardware has been this little 2017 Intel NUC that I bought for $400, back three years when we started this. This thing is pretty underpowered, it's like a 2017 i5, it's got six gigs of RAM, a half a terabyte hard drive and we're running this thing at full scale, as fast as you could do, even our Azure blades or anything like that. You could run it at home right under your desk! Part of that is running a Bitcoin full node, IPFS, and other things, so anyone should be able to get it started.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## What do I need to do to operate Sidetree or on sidetree based DIDs like ION?
We have _install guides_ and there are `Docker` containers for quick install. See more on [github](https://github.com/decentralized-identity/sidetree)

## Am I creating value for Microsoft while I contribute to Sidetree? And they will sell it on their behalf?
We're really wanting to encourage people to install and help us, especially if you're technically capable, or you're a coder or have some aptitude. Kick the tires on it, let us know, find bugs, this is for everyone! This is a public utility, we're not trying to make money on this at all, and so just help it be the best it can be.

## ***Q: How expensive the side tree is to maintain?
In terms of node operation cost, in a light node configuration you could support 40 billion DIDs within ~2TB of space. The protocol is not computationally intense, it's skewed toward bandwidth and storage.

#### *Q: Can you ELI5 for us please... Having trouble wrapping my head around the applications
ELI5=Explain Like I'm 5 years old, [more here](https://www.howtogeek.com/694298/what-does-eli5-mean-and-how-do-you-use-it/)

If you have a DID linked to a personal datastore, people would be able to follow your DID instead of something like a Twitter ID, and pull tweets directly from your datastore. This means apps cannot block your ID or censor your posts. It's the foundation of decentralized apps.
_(@csuwildcat)_

## *Q: Are there examples of Sidetree based identity systems and/or implementors?

### Transmute
Transmute maintains Sidetree ledger adapters for Ethereum, Amazon QLDB, Bitcoin and Hyperledger Fabric. They also support interoperability tests with DID Key, the Universal Wallet Interop Spec, the VC HTTP API, and Traceability Vocabulary. Transmute has built Sidetree.js, an implementation of the Sidetree protocol based on the DIF’s codebase that focuses on modularity: it is a Typescript monorepo where each component of a Sidetree node (Ledger, Content Addressable Storage, Cache database) can be substituted with different implementations that use a common interface.

## SecureKey 
has created a ledger-agnostic [Go implementation](https://github.com/trustbloc/sidetree-core-go) of Sidetree along with [Orb](https://github.com/trustbloc/orb) and [Hyperledger Fabric](https://github.com/trustbloc/sidetree-fabric) variations built on top. [Did:orb](https://trustbloc.github.io/did-method-orb/) enables independent organizations to create decentralized identifiers that are propagated across a decentralized network without reliance on a common blockchain. By extending Sidetree into a Fediverse of interconnected registries, Orb provides the foundation for building digital ecosystems on top of decentralized identifiers using a federated, replicated and scalable approach.

### Microsoft
Microsoft is a primary contributor to [ION](https://identity.foundation/ion/), an open source, public, permissionless implementation of Sidetree on Bitcoin. 
There are several repos and utilities that make working with ION easier, including:
- [ION GitHub repo](https://github.com/decentralized-identity/ion) - main repo for ION node code
- [ION Tools](https://www.npmjs.com/package/@decentralized-identity/ion-tools) - JavaScript libs for Node.js/browsers that makes using DIDs and interacting with the ION network easier
- [ION Install Guide](https://identity.foundation/ion/install-guide/) - step-by-step guide for installing an ION node
- [ION Explorer](https://identity.foundation/ion/explorer/) - graphical interface for viewing DID and other info about the ION network.
In this Q&A there is a [section on ION](#qa-section-ION) that provides basic first answers.

# Q&A section Userinterface

## *Q: What does Sidetree look like?
Currently `Sidetree` is just code, that can be tested and executed in a terminal on the command line or in a browser with programcode available on a webserver. Private key management of Sidetree will look like `wallets`.\
{TBW prio 2}\
_(@henkvancann)_


## *Q: How does it actually work in terms of me as an individual? Could I have multiple IDs? Could I bind my ID to a bitcoin public address?
Yeah, so you can actually have as many IDs as you want in the system. You could have thousands for instance. Actually, there's this concept that we kind of play around with that is, you're going to have probably a couple persona IDs, so well-known persona IDs. This is great for a lot of people. You want a couple IDs in the world that people know are for example Peter, like when Peter signs this with this ID, that's Peter. It's not anyone else, it's not any scammers, imposters, that's him. There's a lot of public stuff you'll tie to that.

You might tie your resume, your podcast, like signed statements you make, like public things you say. That's all good, we all want that and most users want that. Then you have a ton of identifiers, like maybe 99% of them, that we call peer-wise or pairwise identifiers. Where you meet someone, or a company or an app, you get engaged with, where you want to create an ID just for that connection. So that when you create the ID it keeps that connection sort of silent and private between you two, so you're not leaking information.

So it's not just one ID that signs everything and anytime you see any signature you can like triangulate it back to you. What we're trying to do is section those relationships out so that you can keep them as private as you would like between you and your counter parties. To answer your other question about how many keys and stuff, DIDs are an international standard that's being finalized in the W3C.

So this stuff is actually all built on standards, DIDs are represented by this thing called a DID document, which is just a piece of metadata that contains key references and routing endpoints. You can have as many keys in that document as you want, you have say, like a key that maps to your phone and your laptop and other devices you own, because that's the devices you're going to be using your ID with. You can have a bunch of different keys, so it's not like Bitcoin addresses, where there's like a key behind an address or even just multi-sigged, you can have a lot more variety than that.

Then you can also put endpoints that point to certain things. So you can have an endpoint that points to your Twitter profile or you can have an endpoint that points to a personal data store with encrypted data. That's kind of the more future-looking stuff, when we start getting into apps.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## **Q: Will I have some interface for managing all my IDs because it will come down to usability for adoption long-term by the general public?
_I would want something like a one-pass or a Dashlane where I can just manage all my IDs in a single location. Is that coming? Is that coming now or is that coming later?_

We're integrating DIDs into our authenticator app called _Microsoft Authenticator_. If you're familiar with like Google Authenticator or some of the other things, right now it handles 2FA and it's got like your passcodes for your `2FA` stuff for apps. We're adding the ID supports so you'll be able to get DIDs. We're not even like up-levelling the content of the DIDs so you don't have to be super technical, it's going to just get IDs for you when you make new connections, help you manage those keys instate.

We're going to be doing everything we can to augment that process to make it as easy for the average person as possible.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

#### **Q: Is it mandatory to work with Microsoft (Authenticator)?
You don't have to get Microsoft's wallet. The cool thing about the DID system we're building on Bitcoin, you can have an open source wallet that you go download and all the libraries, everything to create these. IDs are completely untethered from any company. So you could say, _"You know what? I don't trust you Microsoft! I'm going to go get this like completely opensource GPL3 thing that I see out there on GitHub and I'm going to run that"_ and that's perfectly fine. In fact, we encourage it.

## *Q: Is there a Sidetree course or webinar available?
These could be some interesting sources:
- [What bitcoin Did 231 podcast](https://www.whatbitcoindid.com/wbd231-daniel-buchner)
- [Daniel Buchner's very quick run down Jan 2021](https://www.youtube.com/watch?v=dZTmGPiLBv8)
- [Orie Steele's SSI Meetup](https://www.youtube.com/watch?v=mk4w2tBTgdE)
Technical folks could also browse through the closed and open [issues](https://github.com/decentralized-identity/sidetree/issues) to get an idea of what has been achieved in the project.

#### **Q: DO you have a virtual playground available for Sidetree? 
Element-DID playground based on Sidetree

https://element-did.com Element DID creation, based on a PPK inception, resulting in a Self Sovereign Identifier that will be anchored through Sidetree on Ethereum.\
_(@henkvancann)_

## *Q: Could Sidetree work for edge computers that need self sovereign identity? How to (selectively) share control with the owners of the device?
What a Sidetree based DID schema like ION provides you to do, is the ability to create identifiers that aren't just for humans or companies, you can create identifiers for intangible, non-living things, like a package. So instead, I can go get a DID for my package and I could put the service endpoint to point to GitHub. From there, I can go scan ION and find all the packets and all the IDs in the system that declare themselves to be say packages and create a decentralized version of npm where I'm no longer reliant on npm happening to exist or to believe my packet is worth indexing. I can create that index myself. I can present the same sort of userinterface you would see on `npm`, but I don't need a centralized identity in the middle of that.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)\

# Q&A section Root of trust

## **Q: What does an ID system gain from a blockchain?
To start off: there are lots of questionable implementations of blockchains. "I would actually harken back to what Satoshi first called Bitcoin before it was blockchain, which was **timechain**. It turns out that `PKI` backs identifiers. An analogy of what one is, is the DNS system.

The identifier in the DNS system is a domain name and then the backing PKI data is your zone file in DNS that lists your named servers, routing information. Then there's the _certificate of authorities_ that have a sort of the backing cryptography. So this is an example of a PKI system. 

Every `PKI` system, if it isn't centralized, like a system where they just kind of decree that this users is usurped, if you want to decentralize that, the most important piece is having a **global immutable append-only log**, because everyone needs to see the state of some identifier. 

If Alice creates an ID and she initially associates her phone with using her ID and a public key on the phone. When she gets a new phone, she's going to switch that key. So everyone needs to be able to see that event, globally and deterministically, or else someone could masquerade as Alice. They could say, "Well, I have her old key so I'm her." You have to have this sort of linear chronology of what happened when, it's a state machine. So what a blockchain does, really elegantly that we never had before, is: **it's an oracle for entering events into a chronology.**"\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)


## *Q: What is it about Bitcoin that seems to fit well with Sidetree? 
_This stuff can be done on Ethereum and other blockchains as well, but just specifically, what is it about Bitcoin that enables this to make it possible to create these IDs?_

First we need to understand [what does an ID system gain from a blockchain](what-does-an-id-system-gain-from-a-blockchain). In brief: it's an oracle for entering events into a chronology. That's exactly what we use the Bitcoin network for. In its most primitive sense, we use Bitcoin to enter in events in a chronology that nodes sort of watch for and compute so they all can understand the state of every ID that's anchored in Bitcoin. So it's very important. 

So why would we pick Bitcoin versus some other blockchain?

Well because we're not actually concerned with any of the super sexy smart contracts, and other stuff. Not to say that there's less interesting stuff in Bitcoin, but we just don't care about features like that, which are not applicable for us. What we most care about is entering stuff in the most immutable, hardened record imaginable and right now, that's Bitcoin. It's pretty hard to argue that isn't Bitcoin, so that's why we use it, is because it has those attributes and it suffices, it does exactly what we need it to do.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## **Q: How does Sidetree establish the root-of-trust that we need for autonomous identifiers? How does the data persist?
A Sidetree client manages keys and performs document operations on behalf of a DID owner. The Sidetree client needs to comply to [guidelines](https://github.com/decentralized-identity/sidetree/blob/master/docs/spec/guidelines.md#sidetree-operations) to securely, successfully manage a user's DIDs.

It is advised that clients managing DIDs try as best as possible to separate the concepts of Update and Recovery keys. Compromise or loss of Update keys does not permanently imperil a user's control over their DID, where a loss or compromise of a Recovery key will, As such, it is important to create appropriate protections and processes for securing and using each type of key, commensurate with their level of control and risk.\
(_@csuwildcat_)

# Q&A section Identifiers

## **Q: DIDs based on Sidetree could stop SIM-swapping?
Oh yeah, it has this potential. I mean if carriers were able to tie your account to a DID or something hardened, literally an attacker would have to physically come take from you, just like they would have to take your Bitcoin, absolutely! I don't think we have this sort of transient ID problem where it can just be like one button push from an operator on their end switches your account.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## *Q: Is my Sidetree identifier public?
This is a choice. Sidetree could settle the identifiers on a private blockchain, whose network consist of a few federated nodes. If you anchor your Sidetree implementation to a public blockchain like Ethereum or Bitcoin, your identifiers are public. However, the linked data can be hashed and put behind a authentication wall (login + username + 2FA).\
_(@henkvancann)_

## *Q: Is a Sidetree identifier GPDR proof?
Yes, in essence the sidetree protocol has the ability to support all functional features that the management of subject identifiers need, according to the GDPR and contemporary privacy rules, performed by owners, controllers and data-processors. For example the right to be forgotten and the right to be deleted.\
_(@henkvancann)_

## **Q: Does Sidetree support transferable identifiers?
A user can transfer the root-of-trust of an identifier (its public private key pair) to another physical wallet. However you can't rotate the keys of a Sidetree identifier, it's a persistent identifier.\
_(@henkvancann)_\
{TBW prio 1, pls check correctness of answer}

A Sidetree implementation anchors its identifier in ledger systems of choice. That means once that choice has been made you can't transfer the full identity event history of that specific identifier.\
_(@henkvancann)_\
{TBW prio 1, pls check correctness of answer}

# File structure

## *Q: What do we need IPFS for?
To store transactions between - and changes to DDO's. Sidetree is a Layer 2 solution on top of a Layer 1 settlement layer: a blockchain of choice.\
_(@henkvancann)_

# Q&A section Wallets

## *Q: Where can I buy Sidetree coin?
Sidetree is not a crypto currency, neither will implementation of Sidetree be a crypto currency.  Sidetree is a protocol for digital identity using decentralized identifiers.\
_(@henkvancann)_

## **Q: Why does Sidetree mention fees?
_....if it is not a crypto currency system?_

It's an optional feature for implementors. Sidetree implementers may choose to implement protective mechanisms designed to strengthen a Sidetree network against low-cost spurious operations. These mechanisms are primarily designed for open, permissionless implementations utilizing public blockchains that feature native crypto-economic systems.\
[More on fees](https://identity.foundation/sidetree/spec/#proof-of-fee)\
_(@henkvancann)_

## *Q: Do I need a wallet for Sidetree?
Yes and No.\
Yes, Sidetree allows for personal key management and any user that want to have all the autonomous sovereign features of digital identity need a wallet to store and manage the keys of their identifiers safely.\
No, if you rely on a custodial service for the inception and management of your digital identifiers, then you won't need a wallet of your own. The big relevant question in that situation is: why would you use Sidetree in the first place id you're not planning to be autonomous.
_(@henkvancann)_

## *Q: How can I backup the Sidetree identifiers in my wallet?
There is a distintion between the private keys controlling the Sidetree identifiers and the digital data related to the identifiers, like DIDs, DDO's and VCs.

To backup the private keys controlling the identifiers there are various ways to backup a crypto wallet: create a backup file, backup the seed, export a specific private key from the set, etc.\
{TBW prio 2: How to backup the DIDs based on Sidetree, are there general recommendations to be made?}\
_(@henkvancann)_

# Q&A section Signatures

## **Q: Why is Sidetree not checking signatures at observation time for all updates, recoveries, and deactivates?
Because signature checks are computationally expensive, so we defer such compute until resolution time.

## *Q What is the practical use of signatures?
Sidetree relies on JSON Web Signatures for authentication and integrity protection of DID Operations, except for Create, with contains key material and is self certifying. [More](https://identity.foundation/sidetree/spec/#json-web-signatures) on JSON Web Signatures.

# Q&A section Private Key Management

## **Q: Does your public-private-key format matter in Sidetree?
Yes, Sidetree uses [JSON Web key format]().

## *Q: Not your keys, not your identity?
Depends. You can be the subject of an identifier and have no control over the indentifier whatsoever. This is practically the case for all login + usernames you "have" to enter the websites of your service providers. You don't own those identifiers and these identifiers can easily be taken away from you with all the related data and social connections. Example: a Twitter ban.

SSI means control over your own identifier. Two nuances: 
- You can own an identifier you're not subject of. Beware that privacy rules and regulations are very strict and demanding.
- You can be the owner, controller and subject at the same time. With great sovereignty comes great responsibility.\
(_@henkvancann_)\
{TBW prio 3}

## *Q: The wallet is there to store my Sidetree private keys safely, no?
Newly created key material (private and public keys, signatures) in Sidetree is self certifying. The root-of-trust is indeed in the wallet you use to manage the private keys. Whether the wallet stores them safely is mainly dependent of its users behaviour and to a much lesser extent the technical security of a wallet (can it be comprimised?).\
(_@henkvancann_)

# Q&A section Blockchain

## *Q: what does an ID system gain from a blockchain?
I would actually harken back to what Satoshi first called Bitcoin before it was blockchain, which was timechain. It turns out that `PKI`, which is public key infrastructure and that's like the thing that backs identifiers. I'll give you an analogy of what one is today. An existing example is the DNS system.

The identifier is a domain name and then the backing PKI data is your zone file in DNS that lists your named servers, routing information, then there's the certificate of authorities that have the sort of the backing cryptography. So that's an example of a PKI system. Every PKI system, if it isn't centralized, like a system where they just kind of decree that this users is usurped, if you want to decentralize that, the most important piece is having a global immutable append-only log, because everyone needs to see the state of some identifier. Like if Alice creates an ID and she initially associates, say her phone that she has at the time with her ID and a public key on it, when she goes to get a new phone, she's going to switch that key up.

So everyone needs to be able to see that event, globally and deterministically, or else someone could masquerade as Alice. They could say, "Well, I have her old key so I'm her." You have to have this sort of linear chronology of what happened when, it's a state machine. So what a blockchain does, really elegantly that we never had before, is it's an oracle for entering events into a chronology. That's exactly what we use it for. In its most primitive sense, we use Bitcoin to enter in events in a chronology that nodes sort of watch for and compute so they all can understand the state of every ID that's anchored in Bitcoin. So it's very important.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## *Q: So why would we pick Bitcoin versus some other blockchain, like Ethereum or Hyperledger?
Sidetree is settlement layer agnostic. There are different reasons to use either one of those platforms. For ION example we argue that because we're not actually concerned with any of the super sexy smart contracts. What we most care about is entering stuff in the most immutable, hardened record imaginable and right now, that's Bitcoin. It's pretty hard to argue that isn't Bitcoin, so that's why we use it, is because it has those attributes and it suffices, it does exactly what we need it to do. [Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner).

There are also Sidetree implementations on Ethereum and Hyperledger Fabric:
 - Ethereum: https://github.com/decentralized-identity/element
 - Hyperledger Fabric: https://github.com/trustbloc/sidetree-fabric
 
 And there is also an ad-hoc network variation called orb: https://github.com/trustbloc/orb

## *Q: Does Sidetree use a blockchain?
Yes, it could use a global blockchain to provide an ordered settlement layer 1 that has reached consensus over the unique representation of the "truth". \
A Sidetree based on other consensus mechanisms and roots-of-trust would, in theory, be possible (if not exactly efficient!), and blockchain-like data structures such as Amazon's QLDB would also work.
(_@bumblefudge_)

## **Q: What's the difference between Sidetree and blockchain?
Lots, it's a totally different beast. There are only a few similarities, for the record:
- The tree-like structure of Side-tree resembles the Merkle tree in which blockchain tend to store proofs of transaction hashes, and Side tree in turn stores identifier events (hashes).
- Core Proof Files form the signature-chained backbone for the state lineages of all DIDs in the system.
_(@henkvancann)_

Sidetree is however NOT a Merkel Tree system - it doesn't use these Merkle trees anywhere. It's literally just ipfs files of highly compact lists of data that interlink to each other.
(_@csuwildcat_)

## **Q: what's the "tree" in Sidetree if it is not a Merkle tree system?
The Merkle tree concept* has been the inspiration for Daniel Buchner, but he soon abandonned the idea of using Merkletree in the Sidetree architecture.
Nowadays the 'tree' in Sidetree refers too:
1. Sidetree Implementations like Orb might have a tree structure in their `CAS`
2. If you put any anchoring system upright and imagine the hash chained Linked lists that Sidetree anchors to the trunk of these anchoring systems... could imagine a tree growing?
<img src="./images/Sidetree-file-structure.png" alt="Sidetree file structure" border="0" width="300">

Sidetree uses IPFS which in turn uses [Merkle DAGs](https://docs.ipfs.io/concepts/merkle-dag/#merkle-distributed-acyclic-graphs-dags)

\* The tree in _Merkle tree_ stems from the fact that the leaves are all content hashes and the branches 2 hashes combined to a single higher level hash, finally ending in a Merkle root the highest level hash.

**Merkle DAGs are similar to Merkle trees**, but there are no balance requirements, and every node can carry a payload. In DAGs, several branches can re-converge or, in other words, a node can have several parents.

 However, the structure of those files happening to be broken down into any subsequent tree structure isn't relied upon by the protocol. Meaning that non-DAG alternatives to IPFS could work and it would still be `Sidetree` conformant.
 You could use a `CAS` that just compressed and cached the source data in place, hashed it, and request by that hash. The reason it's called the `Content-Addressable Storage (CAS)` component in Sidetree is because all it needs is content addressablility. \
 (_@csuwildcat_) and (_@bumblefudge_)


## *Q: Why does Sidetree need a blockchain? 
_...when it has nodes in a network that could federatively establish consensus?_

The ledger (blockchain) acts as a linear chronological sequencing oracle, which the Sidetree protocol leverages to **order** DID PKI operations in an **immutable** history all observing nodes can **replay** and validate. It is this ability to replay the precise sequence of DID PKI state change events, and process those events using a common set of deterministic rules, that allows Sidetree nodes to achieve a consistent view of DIDs and their DID Document states, without requiring any additional consensus mechanism.
The underlaying blockchain provides the consensus mechanism to come to immutable time-stamped ordering.

## *Q: Every time I want to verify an ID, does something happen on the Bitcoin blockchain? 
_Therefore, do I have to pay some kind of transaction fee?_

No, so one thing that's an interesting about this. When we talk about `PKI` systems, and I'll use the analogy of DNS:\
You don't have change your DNS records when you log into Facebook, right? You change your DNS records very infrequently like when you want to move an IP address. So much like that, the system of DIDs, like maybe when you get a new phone, you want to swap out the public key that was on your old one, for the new phone.

So it's a very infrequent activity. When you go to do authentications, like if you authenticated into an app your DID by signing a public and private key challenge based on the ID, none of that actually touches Bitcoin. In fact, it doesn't even touch ION or any other DID schema based on Sidetree. The ID system that we're helping to build, is completely standalone. That's like once you have your ID and you want to use it, you would go onto the website and the website will assert to you, "Hey, please log in." You would say, "Well, I'm DID123" and what the website's going to do is say, "Well, I don't believe you. I'm going to look that DID up. I'm going to find the keys that I know are associated with it." \
When it does, that look up doesn't incur any Bitcoin cost or anything like that, they're just finding cache data and they say, "Great, I have the keys. Now I'm going to sign something and you're going to be able to answer this challenge if you truly own that ID." \
So that entire activity happened at a third layer like well above, it doesn't touch any blockchain stuff at all.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

## **Q: Will Sidetree put more sensitive data on a public blockchain, like Bitcoin? 

Any other data than just identifiers, that you'd want to expose has nothing to do with ION or Bitcoin. None of that is embedded in Bitcoin. That's completely off and on regular infrastructure. It's up to you what you want to disclose. So when I say registry of IDs, it's mean that ION essentially provides you the ability to iterate over every ID that's been entered into the system. This is pretty cool and it has some interesting applications. One application that I like to throw out there that Devs might resonate with a little bit is like `npm`.\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

# Q&A section Agencies

## *Q: Sidetree is like a better version of two-factor authentication?
Yeah, a better version of two-factor authentication. It gives us an opportunity to do things potentially in the future, better underpinning for things like DNS. It is a global registry, at least ION has the ability to be and I know that sounds scary, it's a global registry of IDs, but when I say registry, what I mean is, every ID in ION is, you know at least the identifier. You might not know anything else about the ID, you don't know that it's a person or a dog on the internet, or anything like that. But you know the ID and the keys. So if you ever ran into that person, you could at least like say, "Hey, prove you're you."\
[Source: What bitocin Did 231](https://www.whatbitcoindid.com/wbd231-daniel-buchner)

# Q&A section ION

ION has its own repository under [DIF](https://identity.foundation/ion). This section intents to clear up the difference between ION and Sidetree and how they relate.

Most Question and Answers about ION are located in its own [github repo](https://github.com/decentralized-identity/ion/blob/master/docs/Q-and-A.md. Below a basic selection to start off with.)

## *Q:  What is ION?
<img src="./images/what-is-ION.png" alt="What is ION?" border="0" width="500">

ION is based on Sidetree - standard.

## *Q: Who owns ION?
Just like Sidetree ION is [open source](https://github.com/decentralized-identity/ion/blob/master/LICENSE). Microsoft has been an important sustaining sponsor, but no more than that.

## **Q: Is ION the only Sidetree implementation?
No,  Sidetree enables scalable DID networks (i.e. ION, Element, Orb) to be built atop any decentralized event record system (e.g. blockchains). 

## *Q: How can I use ION?
We have contributed an open source library for generating DIDs and have opened up our ION node to provide a no-hassle option for anchoring ION DIDs:
- [Generate ION DIDs and keys](https://github.com/decentralized-identity/ion-tools#ionjs)
- [Use the lower-level SDK](https://github.com/decentralized-identity/ion-sdk)
- [Anchor DIDs you generate](https://github.com/decentralized-identity/ion-tools)

## *Q: Who owns the DIDs generated with ION?
Ownership of your DIDs is based on keys you generate locally, and all ION operations are signed with those keys, so even if you use our node for anchoring DID operations (or any other node), you are always in sole control.\
(_@csuwildcat_)

## *Q: How does it work? You need bitcoin transactions for DID, right? So how do BTC transaction fees come into play?
ION doesn't bloat the bitcoin blockchain. It gathers multple proofs of identifier events and anchors them with one single small transaction (and dito fee) on the bitcoin blockchain.\
(_@henkvancann_)

#### *Q: Who pays the fee if it's all decentralised?
Node operators who anchor operation batches must pay BTC txn fees. Current we cover the cost for folks who want to anchor via our node, but you can just do it on your own node at home if you want. Ops are signed with keys only you hold, so it's not like another node has your keys.\
(_@csuwildcat_)
