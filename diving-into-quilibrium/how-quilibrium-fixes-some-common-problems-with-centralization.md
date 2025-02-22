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

# How Quilibrium Fixes Some Common Problems with Centralization

### Preventing Unfair Advantages in Transactions (MEV)

On Ethereum, transactions are first sent to a public waiting area (called the "mempool") before being added to the blockchain. The problem? Since everyone can see pending transactions, some actors can manipulate the system to profit unfairly—a practice called **MEV (Maximal Extractable Value)**.

Some companies offer a solution by keeping transactions private, but this only works if they are the ones confirming the transaction. **Quilibrium eliminates this problem entirely**: it doesn't have a public waiting area at all, and transactions remain private. Additionally, it uses an advanced technique (RPM, or **Random Permutation Matrices**) to mix up transactions in a way that makes it impossible to trace where they come from or where they’re going—even for someone actively trying to analyze the data.

#### Avoiding Centralization in Layer 2 Networks

Many blockchain networks build on Ethereum using "Layer 2" solutions to make transactions faster and cheaper. However, some of these solutions are **too centralized**, meaning a small number of entities control most of the system.

One major example is **Optimism** (and similar systems like Base). Until recently, Optimism didn’t even have fraud detection, meaning users had to trust it completely. While some improvements have been made, there are still issues.

**Quilibrium takes a different approach**:

* Instead of relying on a single Layer 2, it creates multiple independent sections (shards), each responsible for its own data.
* These shards communicate with each other but can’t become too centralized—if a shard doesn’t have enough independent participants, it will **automatically shut down to prevent centralization**.

### Fixing Other Centralization Issues: Wallets and Data Access

Ethereum suffers from other forms of centralization, especially in how users access their accounts (wallets) and search blockchain data (indexers).

**Wallets: Improving Security with Passkeys**

Most Ethereum wallets today require users to store sensitive **private keys**, which are long codes that prove ownership of funds. This system has two major problems:

1. **Security risk** – If someone steals your key, they can steal your funds.
2. **Trust issues** – Many people interact with wallets through web browsers, where fake websites trick users into approving fraudulent transactions.

Quilibrium **uses Passkeys**, a newer authentication method already built into modern devices (like fingerprint or face unlock). Passkeys:

* Store keys securely on a device’s built-in security chip.
* Only work on trusted websites, preventing phishing scams.

This makes wallets much safer and easier to use.

### **Indexers: Decentralizing Blockchain Data Access**

Ethereum transactions and smart contracts generate a huge amount of data, which is difficult to search efficiently. Most people rely on a few centralized companies to organize this data (like Etherscan).

Quilibrium **solves this by making data indexing a core part of the network itself**. It uses a **hypergraph structure** that naturally organizes data in a way that is easy to search—without depending on centralized services.

{% hint style="info" %}
For a more technical explanation of the above pints, see this [forum post](https://quilibrium.discourse.group/t/why-quilibrium-is-a-big-deal/17/4?u=lamat).&#x20;
{% endhint %}
