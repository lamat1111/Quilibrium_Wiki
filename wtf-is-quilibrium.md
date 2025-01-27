---
cover: >-
  https://images.unsplash.com/photo-1597733336794-12d05021d510?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxpbnRlcm5ldHxlbnwwfHx8fDE3MTg3MTQxOTd8MA&ixlib=rb-4.0.3&q=85
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

# WTF is Quilibrium?

By: [Cassandra Heart](https://warpcast.com/cassie) - Source: [Quilibrium official blog](https://paragraph.xyz/@quilibrium.com/q-rude-faq#h-what-the-fuck-is-q)

***

**Quilibrium is a protocol under active development with a core mission to secure every bit of traffic on the web.** We believe that previous attempts at doing this through trusted institutions have failed, evinced by revelations by Snowden and others, as well as through their own actions – one only need to look briefly at Cloudflare's and others' deplatforming before it starts to get a little uncomfortable about their behaviors in playing internet cop. To answer this, you need to solve for securely decentralizing the web – servers, storage, traffic. This is not a challenge I take lightly, and hard tech problems require hard tech answers.

On Christmas Day, 2022, I released the Q Whitepaper, which was essentially a heavily cut down box of cryptographic scraps with relatively inaccessible language. What I was largely trying to achieve with the paper was introduce the distinct components of the network, the way in which they are integrated, and provide deeper reference to where and on what these ideas were founded. If you've been deep in the cryptography research space, very little of Q's whitepaper will feel novel, because it isn't – every idea we have utilized is based on existing, battle tested cryptography. We have even shelved one idea that was too far off the beaten trail – PCAS, because it lacked sufficient peer review on the foundations from which it was born.

However, I consider the whitepaper's complexity to be my greatest mistake, and should have opted for an initial litepaper, a simpler whitepaper, and a thorough yellowpaper. I have tried to correct much of this through the use of interactive documentation and labs on the [Quilibrium](https://www.quilibrium.com) website, but there is still much more work to be done in making this accessible. I do not accept "it's too complex to understand" as a reasonable state to be in, because 1. _I don't believe that anything is too complex to understand_, as 2. it only means I have yet to find the right way to convey the information succinctly enough. _One thing I will never do is tell people they are incapable of understanding_ – I am a firm advocate of the [Lucky 10,000](https://xkcd.com/1053/) philosophy, and I love teaching, as it also helps me understand what I haven't conveyed well enough.

<figure><img src="https://storage.googleapis.com/papyrus_images/61a60f7029fbae5631c7b269529b2229.png" alt=""><figcaption></figcaption></figure>

In short, if you have questions, never feel afraid to ask them – I may not always be able to answer right away, but I do try to answer every question received as thoughtfully as possible. We are past the era of where skepticism of cryptocurrency's existence itself was rightfully met with "you do not understand, I am not engaging in this", because cryptocurrency is now self evident, but rather, skepticism towards specific approaches or protocols is extremely warranted and if pushback rather than an answer is the response given, it warrants _even greater skepticism._

The next article plans to ELI5 everything about Q, so if you're looking for the gentlest introduction we've had yet to the underlying technology, please stay tuned for this.

### How does this differ from other attempts? <a href="#h-how-does-this-differ-from-other-attempts" id="h-how-does-this-differ-from-other-attempts"></a>

There are some famous "world computer" attempts historically:

* Ethereum – a popular platform for smart contracts and finance, but is limited in scalability, and privacy has necessarily been bolt-on.
* Solana – somewhat seen as a runner up to Ethereum in success, but still remains tightly coupled to finance.
* Internet Computer/Dfinity – Entirely different model for scaling, a subnet-based model, and does not provide network or data privacy as an essential component, nor is it performing confidential compute to achieve its goals.
* IPVM – I know a few folks personally from that and the broader teams at Fission, and I'm saddened by the news that they have shuttered. Similar to Dfinity, however, it was an open compute platform, and did not have network or data privacy as an essential component.

The most significant difference comes down to three major concerns: scale, structure, and privacy.

Scale: The scaling design mirrors the "shared-nothing" approach used by ScyllaDB, which enables extremely high horizontal scalability, and the execution context enables extremely fast trustless compute on private data, resulting in a network which can handle applications on the 200,000 messages/second scale needed by iMessage, the petabytes of data needed by social media platforms for image hosting, or the unique rules evaluation needed by a highly customizable massively multiplayer game engine.

Structure: Q is a tabula rasa reinvention of a decentralized network, such that structurally it looks practically nothing like a blockchain – at best, you could think of the global proof sequencing as the blockchain component, but it is more in line with Satoshi's original term used for Bitcoin, in that this component is a timechain.

Privacy: Traffic is anonymized akin to Tor, analytic privacy and transactional settlement is further secured by the [same technique proposed to stop MEV on Ethereum](https://eprint.iacr.org/2022/1037.pdf), and input privacy is provided through a multi-party confidential compute execution environment.

### Why am only I hearing about this all of the sudden? <a href="#h-why-am-only-i-hearing-about-this-all-of-the-sudden" id="h-why-am-only-i-hearing-about-this-all-of-the-sudden"></a>

**You aren't on Farcaster.**

I do not use Twitter – it's rife with scammers which they refuse to shut down, is largely dominated by crabs-in-a-bucket bloodsport, and generally has brought out the worst in people. Quilibrium Inc will never have a Twitter presence, and true to my prior statement, indeed there are scammers imitating both Q and community members, spamming wallet drainer links. Twitter, as is expected, is doing nothing to address this. Farcaster (NB: I am employed at the company developing Farcaster, however they are wholly separate from my work on Q) is a sufficiently decentralized social media platform that has successfully avoided much of these problems with One Simple Trick: you have to pay to have an account.

**We aren't doing social media campaigns.**

Q has been largely grassroots – we never contracted a "KOL" (in fact, I detest the term), have barely participated in any sponsorship or advertising (once, during NFT NYC 2023 to help kick off our KZG ceremony (a process which provided randomness to secure proofs on the network), and a second time, at FarCon 2024), choosing instead to keep development prioritized, communication density high, and audience as blended as possible to help find gaps in where communication and resources could be better
