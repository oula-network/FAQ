---
cover: ../.gitbook/assets/Output and Earning Q&A.jpg
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

# 🪙 Output and Earning Q\&A

{% embed url="https://oula.network/en/" %}

**Q: How to understand the data on the output interface?**

A: The meanings of the data displayed are as follows:

* **Total Output:** The historical total output from the creation of the worker account to 24:00 yesterday (UTC+8).
* **Yest. Output:** The actual total output from 00:00 to 24:00 yesterday (UTC+8).
* **Paid Out:** As of now (UTC+8), the system has paid the amount to this account, updated once daily.
* **Unpaid:** Oula Pool typically completes payments within 24 hours after settlement, except in the following cases:&#x20;
  1. No address settings;&#x20;
  2. Total settlement amount does not reach the minimum payout threshold;&#x20;
  3. Payout settings trigger a 24-hour payment suspension rule;&#x20;
  4. Platform risk control rules triggered;&#x20;
  5. Significant incidents such as hard forks, 51% attacks, other major upgrades, accidents affecting the cryptocurrency, etc.
* **Est. Today Mined Qty:** This value is updated hourly and represents the estimated output for today up to the current time. It is for reference only, with the final settlement as the definitive value.



**Q: Why don't I receive rewards when the logs show that I've mined a block in Aleo mining?**

A: After connecting to the mining pool, you use the proof target set by the pool, which is typically much lower than the proof target on the chain. Therefore, even if the log indicates that a solution has been found, it does not guarantee that a block can be successfully mined on the chain.



**Q: When are the daily output settled?**

A: Typically, settlements begin daily at UTC 00:05.



**Q: Why hasn't my account received automatic payments?**

A: Please check that the configured withdrawal address is correct and ensure the balance is above the minimum payout threshold.



**Q: How does Oula mining pool deduct fees?**

A: The specific fee deduction will be announced before the mainnet launch.



**Q: What is the minimum payout threshold and the fee rate?**

A: This information will be confirmed and announced before the mainnet launch.



**Q: What might cause a reduction in Output?**

A: Aside from issues with the user's mining equipment, the main cause is the increase in chain difficulty.



**Q: How to calculate Aleo Output?**

A: You can estimate the output using the calculator on the mining pool page.



**Q: What should I know about the withdrawal address?**

A: The withdrawal address is the Aleo address. Please ensure the address is correct when binding and that the private key is not leaked.



**Q: Why is the mining machine working, but I can't find the worker or output?**

A: Please verify the following:

* Ensure that the network connection from the miner to the pool is stable.
* Confirm that the mining account and pool address are configured correctly.



**Q: Why is there a big difference between actual mining output and theoretical output?**

A：In the case of fluctuations in network difficulty, actual output might differ significantly from theoretical output. Hence, it is normal and network-wide output will also fluctuate accordingly.



**Q: What is the minimum threshold for small withdrawals?**

A: The minimum threshold for small withdrawals will be confirmed and announced before the mainnet launch.



**Q: Where to obtain the wallet address? Is it universal?**

A: You can obtain the wallet address through Leo Wallet, which is universal. Download link: [Leo Wallet Download](https://www.leo.app/download).



**Q: Where to view the Aleo network data?**

A: Aleo's block explorers support queries, such as [Aleo123](https://aleo123.io/), [Aleoscan](https://testnet.aleoscan.io/), etc.



**Q: Are transaction fees deducted when paying out mining rewards?**

A: The specifics of transaction fees will be confirmed and announced before the mainnet launch.



**Q: Are the earnings currently displayed on Oula in Aleo credits?**\
A: Before the mainnet launch, the earnings displayed are virtual earnings from the test environment. After the mainnet is launched, they will be shown as actual Aleo earnings.



**Q: The payment settings prompt states, "It takes 24 hours to restore the automatic payment function after binding or modifying the withdrawal address." Does it take effect within 24 hours from the start of binding?**\
A: For security reasons, the rules for binding or modifying the withdrawal address are as follows:

1. If the operation is completed before 12:00 PM (UTC+8) on the same day, the automatic payment function will be restored at 12:00 PM (UTC+8) the following day.
2. If the operation is completed after 12:00 PM (UTC+8) on the same day, the automatic payment function will be restored at 12:00 PM (UTC+8) two days later.

Any earnings generated during this period will automatically accumulate in the account.





[**Back to Oula**](https://oula.network/en/login)
