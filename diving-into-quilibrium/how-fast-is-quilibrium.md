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
