---
cover: >-
  https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwyfHxkaWdpdGFsfGVufDB8fHx8MTcyMzUzMjc5NXww&ixlib=rb-4.0.3&q=85
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

# How fast is Quilibrium?

**The Quilibrium network has been tested to handle up to 100 million messages per second (MPS)**, demonstrating its capability to support highly demanding applications such as social networks and financial services for processing payments or trades.

While MPS is not exactly the same as transactions per second (TPS), they are closely related. The actual TPS depends on the number of nodes available to handle the load. Initial estimates, based on previous node count statistics, **suggest a realistic upper bound of 1.5-2.5 million TPS**.

The network's performance scales with the number of shards, with each shard capable of processing approximately 6,000 TPS. The Quilibrium network is designed with a minimum of 256 global shards, and core shards can further divide if needed. Under optimal conditions, these numbers represent the upper bounds for a 256-shard configuration.

It's important to note that while these figures may seem far-fetched compared to other blockchain networks, the difference lies in Quilibrium's unique approach. Unlike networks that use Merkle trees and require strict linearized processing, Quilibrium employs a different method for handling transactions within a shard's frame.

The network doesn't use Merkle trees for transactions in a given shard's frame. Instead, it processes conflict-free transactions in parallel, allowing for significantly higher throughput. This innovative approach enables Quilibrium to achieve its impressive performance metrics.

**As the network develops and more shards are implemented, the potential for even higher transaction speeds increases.** The Quilibrium network is designed to self-organize into optimal conditions, potentially pushing the boundaries of blockchain performance and scalability.

### Transaction Finalization Speed on Quilibrium

Quilibrium (Q) delivers rapid transaction confirmations by leveraging its innovative RPM mixnet, a live transaction inclusion system that bypasses the mempool delays typical of many blockchains.&#x20;

When the node tasked with publishing a transaction’s frame shows it’s active, confirmation is assured as soon as the transaction send completes. What makes this reliable is the parallel processing: even if the primary node drops, multiple others handle the same transactions simultaneously, ensuring uninterrupted inclusion through the mixnet’s design.&#x20;

This contrasts with traditional networks where transactions linger in a mempool awaiting block publication—on Quilibrium, the client stays connected until inclusion is confirmed, offering immediate feedback.

The time to finalize a transaction on Quilibrium varies based on factors like transaction complexity, the hardware speed of nodes in a shard, network latency, and connection reliability.&#x20;

#### Available data highlights:

* Lower Bound: 200 milliseconds (0.2 seconds)
* Upper Bound: 10 seconds (per continuation, if relevant)

_Simple transactions on optimized hardware with a strong network can hit that lightning-fast 200 ms mark, while more intricate operations or suboptimal conditions may push times toward the 10-second ceiling._

### Comparison with Other Blockchains

Here’s how Quilibrium stacks up against Ethereum, Solana, and Kaspa:

<table><thead><tr><th>Blockchain</th><th>Finalization Time</th><th>Key Mechanism</th><th data-hidden></th></tr></thead><tbody><tr><td>Quilibrium</td><td>200 ms - 10 s</td><td>RPM Mixnet + Parallel Nodes</td><td>Varies by shard, hardware, and network</td></tr><tr><td>Ethereum</td><td>12-14 minutes (base)</td><td>Proof of Stake</td><td>Slower but secure; Layer-2s speed it up</td></tr><tr><td>Solana</td><td>~12.8 s (full finality)</td><td>Proof of History + PoS</td><td>~1-2 s practical confirmation</td></tr><tr><td>Kaspa</td><td>1-10 s</td><td>BlockDAG + Proof of Work</td><td>Fast 1-s blocks, high throughput potential</td></tr></tbody></table>

* Ethereum: \
  After its 2022 Proof of Stake shift, base-layer finality takes 12-14 minutes (6 blocks at 12-14 seconds each). Users often treat 1-2 minutes as “confirmed,” but full security lags. It’s built for robustness, not speed.
* Solana: \
  With 400 ms block times and a Proof of History twist, Solana hits full finality in \~12.8 seconds (31 confirmations). Practical confirmations often register in 1-2 seconds, making it a speed leader among high-throughput chains.
* Kaspa: \
  Using a blockDAG, Kaspa achieves 1-second block times, with finality typically between 1-10 seconds. Its design supports massive potential TPS, though its ecosystem is still growing.
