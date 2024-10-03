---
cover: >-
  https://images.unsplash.com/photo-1451187580459-43490279c0fa?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxuZXR3b3JrfGVufDB8fHx8MTcxODcxNDEwNHww&ixlib=rb-4.0.3&q=85
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

# How Quilibrium keeps decentralization?

In many cryptocurrencies, agreement depends on blocks of data arranged in a straight line, with more powerful machines (either through raw computing power or staked tokens) having the most influence. This often leads to a tendency to centralize around those who spend the most money, which isn't good for keeping the system decentralized. For example, Bitcoin is mostly controlled by big mining groups, and Ethereum is moving towards a system where its main token is being replaced by easier-to-use tokens and methods.

What sets Quilibrium apart is how it handles agreement among users. Unlike other systems, in Quilibrium, reaching agreement globally doesn't require expensive hardware. Even a simple device like a Raspberry Pi can do the necessary calculations. The main clock, which keeps track of time, doesn't even need to do these calculations because it's easy to verify its accuracy. Instead, these devices can focus on storing data and providing evidence for information that doesn't change often, like long-term storage of unchangeable data.

So, the type of hardware that's successful in mining on the Quilibrium network can vary widely because the network allows for different levels of complexity in applications. This flexibility is something that other networks can't achieve because of their designs.

<figure><img src="https://images.unsplash.com/photo-1599344941911-9caa7fd29ff5?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxRfGVufDB8fHx8MTcxODc4MjU5NHww&#x26;ixlib=rb-4.0.3&#x26;q=85" alt=""><figcaption></figcaption></figure>

## How Q solves some common centralization problems

By [Cassandra Heart](https://quilibrium.discourse.group/u/cassie/summary) - Source: [Quilibrium forum](https://quilibrium.discourse.group/t/why-quilibrium-is-a-big-deal/17/4?u=lamat)

***

### **MEV**

MEV is an issue on Ethereum because the mempool is transparent and shared. Some RPC providers help sidestep this by having private mempools, at the expense of your transaction being incorporated in the block chain only when those providers are the block producer. Quilibrium does not have a public mempool, transactions themselves are private, and transaction routing in 2.0 is achieved through the use of RPM, a technique involving random permutation matrices (hence its initialism), which performs secure matrix multiplication to shuffle the set of transactions being routed such that origin and destination are unlinkable even at the analytical level by passive or active adversaries.

### **Sequencer Centralization**

Layer 2 centralization is multifaceted – the root cause entirely depends on the construction it uses, and the degree of how severe that centralization is also matters. One example that I have been particularly critical towards previously (in fact, it was one of the main motivations for why I quit Coinbase) is in the form of Optimism’s (and OP forks like Base) optimistic rollups scheme. Until very recently, OP mainnet did not have even fraud/fault proofs, and the only form of viable censorship resistance was strictly from the L1 to the L2 via forced inclusion. While this situation has improved, there are still deficiencies, including ones outside of the scope of L2Beat/Vitalik’s codified stages, but creating an exhaustive list would not serve this reply well. Quilibrium, in terms of Ethereum parlance, can be seen as a hybrid of L1 and L2 approaches into a singular network, except the L1 is strictly global consensus, the L2s are the individual shards with separate data availability and cross-shard messaging. The core shards are necessarily not able to become centralized – they will in fact induce shard halts if they fall under the threshold for minimum replication, whether caused by network failure or intentional exit from replication.

There are other aspects of Ethereum itself suffering from centralization, we have designed the architecture of Quilibrium such that those centralization pressures are alleviated. This shows in two important examples: wallets and indexers.

### **Wallets**

Ethereum necessarily has wallets because securing secp256k1 key material, interacting via web browsers, and reconciling state of accounts requires indirections. In particular, the key material problem has a parallel solution in web standards now (but did not exist in mainstream consumer devices until quite recently) – Passkeys/WebAuthN. Passkeys however utilizes different key types (primarily P-256), and the signature’s message format differs from Ethereum, which produces a significant technical debt burden to overcome, likely never in the form of supporting WebAuthN based EOAs in Ethereum. Browser interactions with wallets are also forcing a lot of trust into the wallet to properly deliver risk-bearing information to the end user: any website can offer transactions to a wallet that would (practically speaking) drain most assets. Despite large warning messages, people are often still tricked into signing transactions from malicious websites imitating official ones. Passkeys is a two-birds approach: the signature payload is not only managed by a secure enclave on the user’s hardware frequently with biometric auth, but the keys are intrinsically bound to their domain of origin – it requires cooperation between the originating domain and the domain wishing to use the key in order for it to be usable, drastically improving the state of security.

### **Indexers**

Indexers are a necessary consequence of the expense of laying out data on the EVM in an efficiently queryable form being too high. These indexers are a centralizing force, leaving many to use a handful of centralized providers. The hypergraph structure of Quilibrium is intentionally designed using the RDF Hypergraph approach outlined in [“Hypergraph based query optimization”](https://ieeexplore.ieee.org/document/7218100), which facilitates building efficient indexes according to the structured format of the data implicitly on the network itself.
