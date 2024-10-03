---
cover: >-
  https://images.unsplash.com/photo-1583772096039-86854dfaf875?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw1fHxnYXMlMjBwdW1wfGVufDB8fHx8MTcxODcxNDM2MHww&ixlib=rb-4.0.3&q=85
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

# Gas prices on Quilibrium

On Ethereum, there's the notion of gas price.&#x20;

Quilibrium isn't different in that respect, node operators are able to calibrate price based on demand/supply, or optionally set their own.&#x20;

These prices are essentially a congestion control, but it's important to recognize that congestion is a different thing for Q.&#x20;

Congestion is localized to core shards rather than the network as a whole. Some node operators may even choose to set their prices to their own algorithm, or to zero, though it would be quite the surprise to do that without some other financial incentive.&#x20;

The biggest difference though is that there is no exposure to the contents of transactions, meaning the entire notion of MEV cannot exist on Quilibrium.
