---
cover: >-
  https://images.unsplash.com/photo-1694009235411-d5c9a5051f97?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxjb25jZW50cmljJTIwcmluZ3N8ZW58MHx8fHwxNzI0MzIyNTE5fDA&ixlib=rb-4.0.3&q=85
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

# How does Quilibrium reward the most efficient nodes?

Introducing... the "Prover Rings" (feature available after 2.0).

Imagine a set of concentric rings. Each ring contains 8 nodes, and the rings extend outward until there are no longer enough nodes to form a complete ring. The nodes with the highest uptime (seniority) and best performance over time are positioned at the core. If a node makes a mistake, such as missing a few ticks of the master clock or providing an invalid proof, a higher-scoring node can move up to replace it.&#x20;

This is why, if you've been running a node since the early days, you have an advantage. You will already have an excellent uptime score, and if you maintain your server well, you should receive the best rewards. \
\
For a complete technical explanation of what Prover Rings are, read: [https://paragraph.xyz/@quilibrium.com/one-ring-to-prove-them-all](https://paragraph.xyz/@quilibrium.com/one-ring-to-prove-them-all)

### Seniority and Penalties in the Prover Rings

When a prover is explicitly part of a prover ring, inactivity incurs penalties that affect their seniority value. These penalties increase quadratically with the number of missed intervals - for example, missing three intervals results in a penalty nine times greater than missing one. While returning to active status stops further penalties from accruing, any subsequent inactivity will trigger new penalties.

If penalties accumulate significantly, provers in the outer rings of the given shard will be promoted based on their precedence. To avoid such situations during planned downtime, you have several options:

**For planned maintenance:**

* Use a graceful shutdown (CTRL+C or SIGINT) for short-term maintenance
* After a graceful shutdown, you have a 1000-frame window to restart without penalties
* For longer downtimes, emit a leave message `qclient config prover pause` to avoid penalties

**For unexpected issues:**

* If experiencing hardware failures, use `the qclient config prover pause` command to prevent penalties, unless you can immediately restart the node
* Avoid improper shutdowns or crashes as these will result in immediate seniority point losses

This system ensures network stability while providing flexibility for necessary maintenance and hardware migrations.

{% hint style="info" %}
See [https://docs.quilibrium.one/start/useful-commands](https://docs.quilibrium.one/start/useful-commands) for more info on the `qclient config prover pause command`
{% endhint %}

### I changed peer keys and configurations over time, can I combine them for seniority? <a href="#h-i-changed-peer-keys-and-configurations-over-time-can-i-combine-them-for-seniority" id="h-i-changed-peer-keys-and-configurations-over-time-can-i-combine-them-for-seniority"></a>

Many node operators experimented with different deployment strategies in order to maximize rewards as the network evolved.&#x20;

To ensure that fairness is possible for operators who have changed peer keys and configurations, the prover slot join request is going to include the option of essentially "combining" multiple prover signatures, such that their seniority is additive, but not overlapping (albeit, overlapping time intervals if both peer keys were active do not count as "extra").&#x20;

So for someone who ran a node during the Dawn era, generated a new key set in the lead up to 1.4.19, and once more did so during 1.4.19, they can combine these keys via a configuration step; such that their initial join request can have greater continuity of seniority for their prover range claim. Instructions on how to perform this step will accompany the 2.0 release guide, and we are working with guide writers to ensure their own instructions will include these steps in conjunction with their upgrade info.

_Source:_ [_https://paragraph.xyz/@quilibrium.com/one-ring-to-prove-them-all_](https://paragraph.xyz/@quilibrium.com/one-ring-to-prove-them-all)
