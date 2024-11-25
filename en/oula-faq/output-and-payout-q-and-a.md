---
cover: ../.gitbook/assets/英文.jpg
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

# 🪙 Output and Payout Q\&A

{% embed url="https://oula.network/en/" %}

**Q: How to understand the data on the output interface?**

A: The meanings of the data displayed are as follows:

* **Total Output:** The historical total output from the creation of the worker account to 00:00 UTC yesterday.
* **Yest. Output:** The actual total output from 00:00 to 24:00 UTC yesterday.
* **Paid Out:** As of now, the system has paid the amount to this account, updated once daily.
* **Unpaid:** Oula typically completes payments within 24 hours after settlement, except in the following cases:&#x20;
  1. No address settings;&#x20;
  2. Total settlement amount does not reach the minimum payout threshold;&#x20;
  3. Payout settings trigger a 24-hour payment suspension rule;&#x20;
  4. Platform risk control rules triggered;&#x20;
  5. Significant incidents such as hard forks, 51% attacks, other major upgrades, accidents affecting the cryptocurrency, etc.
* **Est. Today Mined Qty:** This value is updated hourly and represents the estimated output for today up to the current time. It is for reference only, with the final settlement as the definitive value.

***

**Q: When are the daily output settled?**

A: Typically, settlements begin daily at 00:00 UTC.

***

**Q: Why don't I receive outputs when the logs show that I've mined a block in mining?**

A: After connecting to the mining pool, you use the proof target set by the pool, which is typically much lower than the proof target on the chain. Therefore, even if the log indicates that a solution has been found, it does not guarantee that a block can be successfully mined on the chain.

***

**Q: What might cause a reduction in Output?**

A: Aside from issues with the user's mining equipment, the main cause is the increase in chain difficulty.

***

#### **Q: How to calculate Daily Output?**&#x20;

A: You can estimate the output using the [calculator](https://oula.network/en/tool/calc).

***

**Q: Why is the mining machine working, but I can't find the worker or output?**

A: Please verify the following:

* Ensure that the network connection from the miner to the pool is stable.
* Confirm that the mining account and pool address are configured correctly.

***

**Q: Why is there a big difference between actual mining output and theoretical output?**

A：In the case of fluctuations in network difficulty, actual output might differ significantly from theoretical output. Hence, it is normal and network-wide output will also fluctuate accordingly.

***

**Q: What is the minimum threshold for payout?**

A: The minimum threshold for payout will be confirmed and announced before the mainnet launch.

***

**Q: Are transaction fees deducted when paying out mining rewards?**

A: The specifics of transaction fees will be confirmed and announced before the mainnet launch.

***

**Q: The payment settings prompt states, "It takes 24 hours to restore the automatic payment function after binding or modifying the withdrawal address." Does it take effect within 24 hours from the start of binding?**\
A: For security reasons, the rules for binding or modifying the withdrawal address are as follows:

1. If the operation is completed before 04:00 UTC on the same day, the automatic payment function will be restored at 04:00 UTC the following day.
2. If the operation is completed after 04:00 UTC on the same day, the automatic payment function will be restored at 04:00 UTC two days later.

Any earnings generated during this period will automatically accumulate in the account.

***

**Q: What should I know about the withdrawal address?**

A: The withdrawal address is the corresponding Token address. Please ensure the address is correct when binding and that the private key is not leaked.

***

**Q: Why hasn't my account received automatic payments?**

A: Please check that the configured withdrawal address is correct and ensure the balance is above the minimum payout threshold.

***

**Q: How does Oula mining pool deduct fees?**

A: The specific fee deduction will be announced before the mainnet launch.

***

**Q: What is the minimum payout threshold and the fee rate?**

A: This information will be confirmed and announced before the mainnet launch.





[**Back to Oula**](https://oula.network/en/login)
