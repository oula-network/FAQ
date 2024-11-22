---
cover: .gitbook/assets/英文.jpg
coverY: 0
layout:
  cover:
    visible: true
    size: full
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

# 💡 Oula Platform Q\&A

**Q: Does Oula offer Aleo hosting service?**

A: Kindly contact Oula[ Telegram community admins](https://t.me/oulacommunity) for more information or email us at <mark style="color:blue;">contacts@oula.network</mark>.

***

**Q: What is the difference between local power and effective power?**

A: Local power and effective power may exhibit differences:

Local power: The power committed by the miner over a recent period. \
Effective power: The power committed by the miner that has been successfully verified by the server over a recent period.

Theoretically, these two power values should align. However, factors such as network stability, local operational integrity, and the performance of the graphics card during the commitment process can lead to power loss.

For instance, if your local power is 1M/s and you experience a loss of 20K/s due to various circumstances, your effective power would amount to 980K/s.

***

**Q: How to understand the data on the output interface?**

A: The meanings of the data displayed are as follows:

* **Total Output:** The historical total output from the creation of the worker account to UTC 24:00 yesterday.
* **Yest. Output:** The actual total output from UTC 00:00 to 24:00 yesterday.
* **Paid Out:** As of now (UTC 00:00), the system has paid the amount to this account, updated once daily.
* **Unpaid:** Oula Pool typically completes payments within 24 hours after settlement, except in the following cases:&#x20;
  1. No address settings;&#x20;
  2. Total settlement amount does not reach the minimum payout threshold;&#x20;
  3. Payout settings trigger a 24-hour payment suspension rule;&#x20;
  4. Platform risk control rules triggered;&#x20;
  5. Significant incidents such as hard forks, 51% attacks, other major upgrades, accidents affecting the cryptocurrency, etc.
* **Est. Today Mined Qty:** This value is updated hourly and represents the estimated output for today up to the current time. It is for reference only, with the final settlement as the definitive value.

***







[**Back to Oula**](https://oula.network/en/login)
