---
cover: ../.gitbook/assets/Quai.png
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

# 🔍 Project Q\&A

{% embed url="https://oula.network/en/" %}

#### Q: What is the difference between PoEM and PoW?

**A:**

**Fundamental Principles:**

* **PoW (Proof of Work):** Relies on miners completing complex computational tasks to generate hash values that meet specific difficulty requirements. This process validates the legitimacy of a block, with miners competing to produce a valid hash. The first miner to succeed receives the reward.
* **PoEM (Proof of Entropy Minimum):** Builds upon PoW by introducing the concept of "entropy weighting." Beyond meeting difficulty requirements, PoEM calculates the entropy (randomness) of each block, prioritizing blocks with the lowest entropy for validation and addition to the chain.

**Validation Method:**

* **PoW:** Miners are free to select any block that meets the difficulty threshold. This flexibility can lead to different nodes validating different blocks at the same time, resulting in forks.
* **PoEM:** Nodes calculate entropy weights, ensuring that all nodes prioritize the block with the lowest entropy. This reduces forks and accelerates consensus.

**Forks and Consensus:**

* **PoW:** Due to delayed block confirmation among nodes, forks are common, and the network requires extra time to select the main chain and reach consensus.
* **PoEM:** Nodes share a consistent judgment of block weights, allowing them to quickly converge on the same "optimal" block, avoiding forks and enhancing stability.

**Speed and Efficiency:**

* **PoW:** Adding each block depends on miners’ computational power and network confirmation, resulting in delays.
* **PoEM:** The entropy weight mechanism enables nodes to immediately determine the next block, reducing consensus time and improving efficiency.

**Summary:** PoEM optimizes PoW’s consensus process by introducing entropy weighting, enabling faster and more stable network consensus, minimizing forks, and reducing confirmation delays.

***

#### Q: What are the formulas for QUAI and QI rewards, and why do strategies differ across phases?

**A:**

**QUAI and QI Distribution Mechanism:**

* **QI:** Its issuance is linearly proportional to mining difficulty. As difficulty increases, QI issuance grows at a fixed rate. Thus, QI rewards increase significantly during high-difficulty phases.
* **QUAI:** Its issuance follows a logarithmic decrease relative to mining difficulty. As difficulty rises, QUAI issuance grows more slowly or even decreases. This makes QUAI more advantageous during low-difficulty phases.

**Strategy for Maximizing Rewards:**

* **High Difficulty (High Hashrate):** Prioritize mining QI for higher rewards. Convert existing QUAI to QI to maximize returns.
* **Low Difficulty (Low Hashrate):** Prioritize mining QUAI for greater relative benefits. Convert existing QI to QUAI to enhance overall profitability.

***

#### Q: What is the transfer speed from Region 1 to Region 2?

**A:** The transfer speed between the two regions is consistent, with blocks generated every 10 seconds.

***

#### Q: How can I query Quai using the block explorer?

**A:** You can access the Quai block explorer for queries via this link: [Quai Block Explorer](https://quaiscan.io).

***

#### Q: What wallets are recommended?

**A:** Recommended wallets for Quai:

* [Pelagus Wallet](https://pelaguswallet.io/)
* [Koala Wallet](https://koalawallet.io/)





[**Back to Oula**](https://oula.network/en/login)
