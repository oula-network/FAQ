---
hidden: true
cover: ../.gitbook/assets/aleo.jpg
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

# 🤖 Aleo Mining Tutorial - HiveOS

{% embed url="https://oula.network/en" %}

> &#x20;❕ [ALEO](https://www.aleo.org/) is a blockchain project that integrates Proof of Work (PoW) and Proof of Stake (PoS) consensus mechanisms to offer highly private smart contract capabilities. It utilizes advanced Synthesis Puzzle technology to ensure transaction privacy and security. Aleo focuses on developing decentralized applications and provides efficient and secure privacy protection solutions.



Please read the mining tutorial carefully and follow the steps to connect the mining machine to the mining pool.

{% hint style="info" %}
Please stay updated with [<mark style="color:blue;">**OULA's official website**</mark>](https://oula.network/en) announcements and use the latest version of the software client for optimal technical service and higher Token output.
{% endhint %}

### **Environment Setup**

*   Download and install the latest version of [HiveOS](https://hiveon.com/install/).&#x20;

    * GPU Image Version: <mark style="color:red;">**HiveOS-0.6-227-stable**</mark>&#x20;
    * Distro Base: <mark style="color:red;">**Ubuntu 20.04.6 LTS**</mark>

    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Note: Online upgrades cannot be performed using older image versions. Please install the new image directly and ensure the system is running Ubuntu 20.04.
{% endhint %}

* Upgrade the GCC and G++ compilers with the command:

<pre class="language-sh"><code class="lang-sh">apt install software-properties-common
<strong>add-apt-repository ppa:ubuntu-toolchain-r/test
</strong>apt update
apt install gcc-11 g++-11
</code></pre>

* Set the priority for GCC and G++ with the command:

```sh
update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-11 10
update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-11 10shell
```

* upgrade the NVIDIA driver with the command:

```
nvidia-driver-update
```

### **Account Setup**

* Register for an [**Oula Account**](https://oula.network/en/register) and setup the [**Sub-Account**](https://oula.network/en/pool/manager?tab=subAccount).
* Use the default Aleo Sub-Account name or create a new one as the wallet address.&#x20;

{% hint style="warning" %}
**Sub-account and miner names can be customized but must be globally unique!**&#x20;

**It is recommended to use 2-15 lowercase letters, numbers, or a combination, and the name cannot start with a number.**
{% endhint %}

### &#x20;Wallet Creation

* Go to the "<mark style="color:blue;">**Wallet**</mark>" tab and click the "Add Wallet" button.
* Select the corresponding cryptocurrency.
* Enter the Wallet Address ([<mark style="color:blue;">**Oula Sub-Account Name**</mark>](https://oula.network/en/pool/manager?tab=subAccount)) and Name (customizable).
* Click the "Create" button.

### Flight Sheet Creation

* Go to the "<mark style="color:blue;">**Flight Sheet**</mark>" tab and click the "Add Flight Sheet" button.
* Select the corresponding cryptocurrency.
* Choose the wallet name created above.
* Select "Mining Software Configuration."
* Choose Custom, click "<mark style="color:blue;">**Configure Mining Software**</mark>," and enter the following parameters:
  * Mining Software Name: `oulapool`
  * Installation Link: `https://oula-hiveos.oss-ap-southeast-1.aliyuncs.com/oulapool-v1.7.tar.gz`
  * Encryption Algorithm: `aleo`
  * Wallet and Miner Template: `%WAL%.%WORKER_NAME%`
  * Pool Address: `wss://aleo.oula.network:6666`
* Click the "Create Flight Sheet" button to complete the flight sheet setup.

### **Monitoring and Yield Viewing**

Once your mining machine is running stably and submitting solutions, you can check the worker's operational status, output details and payment details under [**Worker**](https://oula.network/en/pool/manager?tab=miner) and [**Output / Payout**](https://oula.network/en/pool/manager?tab=output) by switching to the corresponding sub-account.





[**Back to Oula**](https://oula.network/en/login)
