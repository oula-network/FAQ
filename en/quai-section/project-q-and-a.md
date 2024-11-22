---
cover: ../.gitbook/assets/aa.png
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

**Q: What is the difference between host power and effective power? Why are there two types of power?**

**A**:

* **Host Power**: The actual computational power of the hardware.
* **Effective Power**: The power required by the blockchain, calculated based on its difficulty.

**Reason for the difference**: Mining pools assign tasks with lower difficulty. Some lower-performance workers can complete these tasks but may not meet the blockchain’s required difficulty, leading to discrepancies between the two metrics.

***

**Q: What are the differences between PoEM and PoW mechanisms?**

**A**:

**Basic Principle**:

* **PoW**: Proof-of-Work mechanism requires miners to perform complex calculations to generate a hash value meeting the difficulty requirements to validate blocks.
* **PoEM**: Builds on PoW by introducing "entropy weighting," where nodes prioritize blocks with lower entropy to quickly reach consensus.

**Validation Method**:

* **PoW**: Nodes can select any block meeting the difficulty requirements, which might lead to forks.
* **PoEM**: Nodes evaluate entropy values and always select the block with the lowest entropy, reducing fork probability.

**Forks and Consensus**:

* **PoW**: Forks occur, requiring extra time to determine the main chain, delaying final consensus.
* **PoEM**: With unified entropy evaluation, consensus is quickly reached, enhancing network stability.

**Speed and Efficiency**:

* **PoW**: Block confirmation depends on computational power and requires time to achieve consensus, resulting in delays.
* **PoEM**: The entropy-weighting mechanism reduces confirmation time, improving efficiency and resolving forks promptly.

**Summary**: PoEM optimizes PoW processes by enhancing speed and stability, reducing forks and delays.

***

**Q: Why do Quai and Qi reward strategies vary across stages?**

**A**:

**Reward Characteristics**:

* **Qi**: Its issuance grows linearly with mining difficulty, providing higher rewards during high-difficulty phases.
* **Quai**: Its issuance grows logarithmically and decreases as difficulty rises, making it more rewarding at lower difficulty levels.

**Reward Strategies**:

* **High Difficulty Phase**: Prioritize mining Qi and converting existing **Quai** to Qi for higher rewards.
* **Low Difficulty Phase**: Prioritize mining **Quai** and converting Qi to **Quai** to maximize **Quai** rewards.

***

**Q: Does transferring funds from Region 1 to Region 2 happen faster?**

**A**: The transfer speed is the same, requiring approximately 10 seconds per block.

***

**Q: What blockchain explorers and wallet tools are recommended for the Quai network?**

**A**:

* **Explorer**: [Quai Explorer](https://cyprus1.colosseum.quaiscan.io/)
* **Wallets**:
  * [Pelagus Wallet](https://pelaguswallet.io/)
  * [Koala Wallet](https://koalawallet.io/)



[**Back to Oula**](https://oula.network/en/login)
