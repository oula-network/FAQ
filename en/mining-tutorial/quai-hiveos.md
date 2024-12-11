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
    visible: true
  pagination:
    visible: true
---

# 🤖 Quai - HiveOS

Please read the mining tutorial carefully and follow the steps to connect the mining machine to the mining pool.

{% hint style="info" %}
Please stay updated with [<mark style="color:blue;">**OULA's official website**</mark>](https://oula.network/en) announcements and use the latest version of the software client for optimal technical service and higher Token output.
{% endhint %}

### **Environment Setup**

*   Download and install the latest version of [HiveOS](https://hiveon.com/install/).&#x20;

    * GPU Image Version: <mark style="color:red;">**HiveOS-0.6-227-stable**</mark>&#x20;
    * Distro Base: <mark style="color:red;">**Ubuntu 20.04.6 LTS**</mark>

    <figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
**Note:** Do not use the firmware online upgrade feature. Please reinstall the new firmware and ensure that the system version is Ubuntu 20.04.
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
update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-11 10
```

* upgrade the NVIDIA driver with the command:

```
nvidia-driver-update
```

{% hint style="info" %}
If you encounter any issues during the setup or use of HiveOS, or if you have other configuration-related questions, we recommend checking out the [HiveOS Official Guide](https://hiveon.com/knowledge-base/guides/) for detailed instructions and support. The guide covers solutions for both beginners and advanced users, helping you manage your mining environment more effectively. 📘
{% endhint %}

### **Account Setup**

* Register for an [**Oula Account**](https://oula.network/en/register) and setup the [**Sub-Account**](https://oula.network/en/pool/manager?tab=subAccount).
* Use the default Aleo Sub-Account name or create a new one as the wallet address.&#x20;

{% hint style="warning" %}
**Sub-account and miner names can be customized but must be globally unique!**&#x20;

**It is recommended to use 2-15 lowercase letters, numbers, or a combination, and the name cannot start with a number.**
{% endhint %}

### &#x20;Wallet Creation

* Go to the "<mark style="color:blue;">**Wallet**</mark>" tab and click the "<mark style="color:blue;">**Add Wallet**</mark>" button.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

*   Set the corresponding parameters.

    * Coin `QUAI`
    * Address [`Created Oula Sub-Account Name`](https://oula.network/en/pool/manager?tab=subAccount)
    * Name `oula-quai-miner`

    <figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>
* Click the "Create" button.

### Flight Sheet Creation

* Go to the "<mark style="color:blue;">**Flight Sheet**</mark>" tab and click the "<mark style="color:blue;">**Add Flight Sheet**</mark>" button.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

*   Set the corresponding parameters.

    * Coin `QUAI`
    * Wallet `oula-quai-miner`
    * Pool `Configure in miner`
    * Miner `Custom`
    * Name `oulapool`

    <figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>
*   Click the "<mark style="color:blue;">**Setup Miner Config**</mark>" button, enter the following parameters and Click the "<mark style="color:blue;">**Apply Changes**</mark>" button to save the configurations.

    * Miner Name: `oula-quai-miner`
    * Installation URL: [`https://oula-pool.oss-ap-southeast-1.aliyuncs.com/quai/Hiveos/oula-quai-miner-vx.y.z.tar.gz`](https://oula-pool.oss-ap-southeast-1.aliyuncs.com/quai/Hiveos/oula-quai-miner-vx.y.z.tar.gz)\
      (Update the link address according to [the latest version number](https://app.gitbook.com/s/yseWjqJcypCcEst0oC22/), e.g., v1.0.0)
    * Hash algorithm: `progpow-quai`
    * Wallet and worker template: `%WAL%.%WORKER_NAME%`
    * Pool URL: `stratum://quai.oula.network:3333`

    <figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
* Click the "Create Flight Sheet" button to complete the flight sheet setup.
* Apply the added miners to the created flight sheet.

### **Monitoring and Yield Viewing**

Once your mining machine is running stably and submitting solutions, you can check the worker's operational status, output details and payment details under [**Worker**](https://oula.network/en/pool/manager?tab=miner) and [**Output / Payout**](https://oula.network/en/pool/manager?tab=output) by switching to the corresponding sub-account.





[**Back to Oula**](https://oula.network/en/login)
