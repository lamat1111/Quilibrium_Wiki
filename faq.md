# FAQ

### General 2.0 FAQ

<details>

<summary>When is the 2.0 launch?</summary>

It was originally planned for July 20, but testing is taking a bit longer than anticipated. Overall however, things are going well as seen on [status.quilibrium.com](https://status.quilibrium.com). New ETA is Aug 7.

</details>

<details>

<summary>Why is the 2.0 launch important? What does it enable?</summary>

It is important of many ways with some of the key highlights being:

* It enables the development of apps/tokens
* It completes the key privacy features of QUIL
* It allows for the transferring of native QUIL tokens and cross bridging between wQUIL (ERC20)
* It enables node-runners to auto mint QUIL tokens without needing to run mint commands

</details>

<details>

<summary>Is there a Q explorer (like Etherscan)?</summary>

Not yet, but there can be one to a limited degree. The network has overall active proof state, prover rings, total supply – these are things that anyone can see. The contents of transactions or their settled states are however invisible unless you possess relevant key material to the transaction. It is likely someone will build an explorer, and it will be globally less useful than Monero's explorers for transaction info, but could be made useful for individuals running multi-legged auth operations to see their own personal state.

Note the above applies only to native QUIL. wQUIL remains queryable via block explorers.

</details>

<details>

<summary>What happens to wQUIL (ERC20) after the 2.0 launch?</summary>

wQUIL will remain active and transferrable/tradable as it is today. QUIL holders will continue to be able to bridge to wQUIL as they wish, and wQUIL holders will be able to bridge back to native QUIL with the 2.0 launch.

</details>

<details>

<summary>What is next on the Q roadmap after 2.0?</summary>

After the 2.0 launch, the focus will be building out developer documentation and the fundamental services of the Internet that people enjoy such as file storage (i.e., S3), executable code, and domain services.

</details>

<details>

<summary>What are people building on Q right now?</summary>

Not everything is ready to share publicly just yet but several public community projects include collectables/NFTs, node managers, Howler (flagship demo app, Discord alternative) and decentralized exchanges.

</details>

<details>

<summary>Is there developer documentation available?</summary>

There is some, but more will be coming when Cassie can shift focus post-2.0 launch. This documentation is available in the Labs and docs tabs on Quilibrium.com, and some videos that Cassie has streamed. [YouTube Playlist](https://www.youtube.com/watch?v=eZ6oRyMAB3c\&list=PLnhsXXDZIsK7CTdt14TM9fo9KcT3GzPRf) Twitch

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

Answer pending

</details>

<details>

<summary>Will the Twitch streams continue? Where can I access previous recordings?</summary>

Answer on whether they will continue pending Previous recordings are available here: [Collection of Video Links - General - Quilibrium Forum](https://forum.quilibrium.com/t/collection-of-video-links/302)

</details>

<details>

<summary>What are the official Q socials? How come there is no official X, Telegram, Discord?</summary>

This discourse is intended to be the primary comms channel for the near term. It was a decision early in the project to embrace as much decentralized tools as possible, and if not present, that their absence serves as a forcing function to make them exist. Discord especially, as the project started from a discord alternative. Regarding regulations: Q Inc are firm about compliance, which is why they don't enter into deals with VCs regarding the token, ensured that the token was not launched with some special parties but rather earned by protocol only, and specifically never encourage treating QUIL as a speculative asset. It is a utility token for the network. They do look forward to greater regulatory clarity in the United States, as it has been an incredibly difficult position to be in, but FIT 21 is incredibly promising, and they would be the first (to Cassie's knowledge) project founded in the United States that complies with it out the gate.

</details>

<details>

<summary>What is the performance of the network at 2.0? How does it compare to other L1s?</summary>

Part of the test suite actively being drilled through in the release process for 2.0 is security related, another part is performance related. When this has concluded, we will have firm numbers and call outs for places of improvement in subsequent updates.

See also [how-fast-is-quilibrium.md](how-fast-is-quilibrium.md "mention")

</details>

<details>

<summary>How many developers are contributing to Q right now?</summary>

Cassie Heart is the primary maintainer (hence the colloquial "BDFL" joke), but there are some folks who have contributed huge parts to the protocol, such as the Rust VDF implementation and some consensus bug fixes.

</details>

### Node running FAQ

<details>

<summary>I'm running a Q node. What do I need to do at the 2.0 launch to ensure I have updated correctly?</summary>

The upgrade process is the same as previous versions. If you are running the release\_autorun.sh, your node should update automatically at the 2.0 release.

</details>

<details>

<summary>How often will node releases follow 2.0?</summary>

Quilibrium will move into a longer quarterly release cycle after 2.0, barring bugfixes.

</details>

<details>

<summary>Do the minimum node requirements change with 2.0?</summary>

No. 4 dedicated cores, 8GB of RAM remains the recommended minimum. Rewards scale with hardware performance.

</details>

<details>

<summary>I lost my keys/config/store files. Have I lost my QUIL?</summary>

It depends. If you were operating after v1.4.19, you will need your store directory along with the keys and config yml files to access your QUIL. Prior to that, only the keys and config were required. If you only have the config file, you may be able to regenerate the key file, but this is only for pre 1.4.19. If you do not have the config file, there is no way to recover the QUIL.

</details>

<details>

<summary>What files need to be backed up on nodes after 2.0?</summary>

You should continue to backup the entire \~/ceremonyclient/node/.config directory as before (note the "." in config). This will ensure access to your QUIL and keep your priority rank as a prover.

</details>

<details>

<summary>How many nodes are online right now?</summary>

Rough approximation of node count can be seen here: [https://dashboard.quilibrium.com](https://dashboard.quilibrium.com)

</details>

<details>

<summary>What are the average specs and earnings?</summary>

Last time stats were run on this was an average core count of 29 cores. Earnings is tougher to say.

</details>

<details>

<summary>How will rewards change with 2.0?</summary>

The network will operate under the full Proof of Meaningful Work reward basis, where prover rings factor in on earnings rate. A full explainer on this is near the end of [Quilibrium Blog | Proof of Meaningful Work](https://quilibrium.com/blog/proof-of-meaningful-work).

</details>

<details>

<summary>How do I access/claim QUIL that was previously locked (post 1.4.17)?</summary>

1.4.17 to 1.4.18: They will be immediately registered under the address of reward with the deployment of the token application. No time limits are involved. 1.4.19 to 1.4.21: The token application's mint function will have a short lived window of one week to complete the claim before strictly only allowing 2.0 protocol proofs for the mint function (during the one week window it will permit either).

</details>

<details>

<summary>Is there a time limit to claiming pre 2.0 rewards?</summary>

Only for tokens obtained during 1.4.19/20/21. You will have 1 week to claim these following the complete deployment of 2.0.

</details>

### QUIL Token FAQ

<details>

<summary>I don't run a node. How do I create a native QUIL wallet?</summary>

There isn't a wallet per-say. You have an Account and that account owns tokens. Your account is created/set up using Passkeys which is handled by your browser and each application.

</details>

<details>

<summary>What is the circulating supply at 2.0?</summary>

Approximately 750 million (minus an estimated 50 to 100 million lost from missing backups and lost vouchers)

</details>

<details>

<summary>What is the emissions rate at 2.0? Is there updated tokenomics documentation?</summary>

Answer pending

</details>

<details>

<summary>How many tokens are considered lost?</summary>

There are an estimated 50 to 100 million QUIL permanently lost due to missing backups and lost vouchers.

</details>
