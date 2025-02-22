# FAQ

General 2.1 FAQ

<details>

<summary>When is the 2.1 launch?</summary>

ETA is early Q1 2025.

</details>

<details>

<summary>Why is the 2.1 launch important? What does it enable?</summary>

It is important of many ways with some of the key highlights being:

* It enables the development of apps/tokens
* It completes the key privacy features of QUIL

</details>

<details>

<summary>Is there a Q explorer (like Etherscan)?</summary>

[Official Dashboard](https://dashboard.quilibrium.com/)\
[Unofficial Explorer built by Qrim](https://qrim.io/)

</details>

<details>

<summary>What happens to wQUIL (ERC20) after the 2.1 launch?</summary>

wQUIL will remain active and transferrable/tradable as it is today. QUIL holders will continue to be able to bridge to wQUIL as they wish, and wQUIL holders will be able to bridge back to native QUIL with the 2.1 launch.

</details>

<details>

<summary>What is next on the Q roadmap after 2.1?</summary>

After the 2.1 launch, the focus will be building out developer documentation and the fundamental services of the Internet that people enjoy such as file storage (i.e., S3), executable code, and domain services.

</details>

<details>

<summary>What are people building on Q right now?</summary>

Not everything is ready to share publicly just yet but several public community projects include collectables/NFTs, node managers, Quorum (flagship demo app, Discord alternative) and decentralized exchanges.

To see apps that are already available, check the [ecosystem page](https://quilibrium.one/ecosystem/).

</details>

<details>

<summary>Is there developer documentation available?</summary>

There is some, but more will be coming when Cassie can shift focus post-2.0 launch. This documentation is available in the Labs and docs tabs on [Quilibrium.com](https://quilibrium.com/), and some videos that Cassie has streamed ([YouTube Playlist](https://www.youtube.com/watch?v=eZ6oRyMAB3c\&list=PLnhsXXDZIsK7CTdt14TM9fo9KcT3GzPRf)).

</details>

<details>

<summary>Is there going to be a Q native DEX?</summary>

Absolutely :wink:

</details>

<details>

<summary>What is the status of Q Inc?</summary>

It's a registered C Corporation in Delaware. Funding wise, the seed round is still in progress, but Cassie can't mention much detail on this until it concludes in some form.

</details>

<details>

<summary>Does Q have any marketing plans?</summary>

Marketing and hiring starts after the 2.1 launch, when the Q Inc funding round comes to an end.

</details>

<details>

<summary>What is the performance of the network at 2.1? How does it compare to other L1s?</summary>

Part of the test suite actively being drilled through in the release process for 2.0 is security related, another part is performance related. When this has concluded, we will have firm numbers and call outs for places of improvement in subsequent updates.

See also [how-fast-is-quilibrium.md](diving-into-quilibrium/how-fast-is-quilibrium.md "mention")

</details>

<details>

<summary>How many developers are contributing to Q right now?</summary>

Cassie Heart is the primary maintainer (hence the colloquial "BDFL" joke), but there are devs who have contributed huge parts to the protocol, such as the Rust VDF implementation and some consensus bug fixes.

With the 2.1 launch, Q Inc will begin hiring more developers.

</details>

### Node running FAQ

<details>

<summary>How often will node releases follow 2.1?</summary>

Quilibrium will move into a longer quarterly release cycle after 2.1, barring bugfixes.

</details>

<details>

<summary>Do the minimum node requirements change with 2.1?</summary>

No. 4 dedicated cores, 8GB of RAM remains the recommended minimum. Rewards scale with hardware performance.

</details>

<details>

<summary>I lost my keys/config/store files. Have I lost my QUIL?</summary>

It depends. If you were operating after v1.4.19, you will need your store directory along with the keys and config yml files to access your QUIL. Prior to that, only the keys and config were required. If you only have the config file, you may be able to regenerate the key file, but this is only for pre 1.4.19. If you do not have the config file, there is no way to recover the QUIL.

</details>

<details>

<summary>What files need to be backed up on nodes after 2.1?</summary>

You should continue to backup the entire \~/ceremonyclient/node/.config directory as before (note the "." in config). This will ensure access to your QUIL and keep your priority rank as a prover.

</details>

<details>

<summary>How many nodes are online right now?</summary>

A rough approximation of node count can be seen on the [Q dashboard](https://dashboard.quilibrium.com/).

</details>

<details>

<summary>How will rewards change with 2.1?</summary>

The network will operate under the full Proof of Meaningful Work reward basis, where prover rings factor in on earnings rate. A full explainer on this is near the end of [Quilibrium Blog | Proof of Meaningful Work](https://quilibrium.com/blog/proof-of-meaningful-work).

</details>

### QUIL Token FAQ

<details>

<summary>I don't run a node. How do I create a native QUIL wallet?</summary>

There isn't a wallet per-say. You have an Account and that account owns tokens. Your account is created/set up using Passkeys which is handled by your browser and each application.

There are however wallets maintained by third party developers. Check the [ecosystem page](https://quilibrium.one/ecosystem/).

</details>

<details>

<summary>What is the circulating supply at 2.1?</summary>

Check the [Q dashboard](https://dashboard.quilibrium.com/).

</details>
