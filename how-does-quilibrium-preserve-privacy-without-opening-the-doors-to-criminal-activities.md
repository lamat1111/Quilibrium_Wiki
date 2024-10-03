---
cover: >-
  https://images.unsplash.com/photo-1624969862644-791f3dc98927?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxjeWJlciUyMGNyaW1lfGVufDB8fHx8MTcxODcxNDUyOHww&ixlib=rb-4.0.3&q=85
coverY: 0
layout:
  cover:
    visible: true
    size: hero
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# How does Quilibrium preserve privacy without opening the doors to criminal activities?

_Quilibrium is a privacy preserving network, with a cryptographic accumulator bundle within each coin that a user can utilize to assert funds are not from illicit/sanctioned addresses. To that end, we retain privacy, but also provide compliance. Our goal is not to aid criminals, we don't promote the use of the network for criminal activity, and we take good faith measures to help people use the network for legitimate purposes while maintaining their privacy._

## High level explanation

By [Cassandra Heart ](https://quilibrium.discourse.group/u/cassie/summary)- Source - [Quilibrium forum](https://quilibrium.discourse.group/t/how-does-q-preserves-privacy-without-opening-the-doors-to-criminal-activities/112/3?u=lamat)

### Background

One of the defining features of Q’s shard strategy is it provides nescience to the data being stored – that, assuming no data is revealed about the shard, the operators are effectively blind to it. This is a strategy that applies as much to E2EE messaging providers as it does AWS S3 when employing KMS (assuming they are both telling the truth and are also impervious to attacks against their HSM – although we know the latter isn’t true given their manufacturer has been previously exposed by Snowden to be SIGINT enabled). This feature is one that often leads to this question, because if there are no means to mediate this, the end state of the network would be one largely adopted by those who would wish to exploit it (e.g. Freenet). Let’s dive into how the interaction model on Q works by default, how this makes it sub-optimal to be abused for the most concerning use case, and then how we address it on multiple levels.

### Interaction-Specific Considerations <a href="#interaction-specific-considerations-2" id="interaction-specific-considerations-2"></a>

The default interaction model for core shards and data settlement is not the most optimal design – rather, it is a balance to serve many different kinds of applications. For text-based messaging, text content and social graphs on social media, and general financial applications, this is a good balance to strike. For more involved use cases, like file hosting (especially image hosting), this default is suboptimal to the point you would probably prefer an alternative.

### Example Application <a href="#example-application-3" id="example-application-3"></a>

Consider the following: a simple messaging application starting off with text-only content sets an upper limit on characters so that they can be neatly indexed and searchable for the client. Images do not have a searchability requirement (or if they do, it often relies on ML which is out of scope for a simple application). If the application were to try to shoehorn in image support by bootstrapping off the character-limited messages (e.g. via base64 encoding the image into the message content), it would need to perform chunking of the image into several messages, and incur a cost on search indexes for no benefit.

Needless to say, image processing would preferably take a slightly different path, especially one that can optimise for the end user in various ways (e.g. thumbnail low-fidelity image for fast download, higher quality loaded lazily).

### Let’s cut to the chase: the worst kind of criminal <a href="#lets-cut-to-the-chase-the-worst-kind-of-criminal-4" id="lets-cut-to-the-chase-the-worst-kind-of-criminal-4"></a>

To perform that image processing via raw garbled circuits would be a tremendously slow operation, and not to mention, you encounter a really thorny problem – while in the U.S. there is precedent that service providers do not have a responsibility for user generated content prior to being alerted, some jurisdictions, such as the E.U., have other laws which do mandate some responsibility and liability. To remediate this problem, there are MPC techniques which can rely on some initial client-side processing to reduce the strain on both the end user (not having to invoke a garbled circuit) and the network itself (not having to process the garbled circuit), that can work hand-in-hand with organizations that are legally authorised to handle and produce tools to disambiguate content with strict liability concerns. Apple, despite having a problem in trying to effectively communicate how this solution was far better than the approach they currently use with iCloud, had designed such an MPC process: [https://www.apple.com/child-safety/pdf/CSAM\_Detection\_Technical\_Summary.pdf 2](https://www.apple.com/child-safety/pdf/CSAM\_Detection\_Technical\_Summary.pdf)

As a net result, image hosting can be made far faster, preserve user privacy, _and solve for compliance regarding strict liability laws_ through the use of specialised intrinsics. These are the intrinsics we intend to have in place before there is a purpose-built image hosting application on the network.

### So what about the slow path? <a href="#so-what-about-the-slow-path-5" id="so-what-about-the-slow-path-5"></a>

Thankfully, criminals often take the path of least resistance: consider how many times criminal activity is caught because they organise over unencrypted, publicly accessible groups. But what if someone were to use the slow path of chunking base64 content through this hypothetical messaging app?

First, this is a problem for any network, encrypted or not – there are issues with Bitcoin itself having data encoded into the block chain that imparts legal issues depending on the nation where the miner is operated. Where things differ on Quilibrium is that unlike Bitcoin, where every miner must have all valid active state of the network stored, or public centralised social media applications where content moderation is either a farce or a Kafkaesque nightmare to navigate, if such a legally problematic core shard is revealed to exist – e.g. the core shard decryption key has been revealed by the owner, and/or certified by a compliance entity (like the NCMEC) to contain such content (verifiable encryption can enable such a certification), node operators can maintain their own blacklist of core shards they will not replicate. To simplify this process, we expect over time there will be many different lists that node operators will likely synchronise with based on their jurisdiction.
