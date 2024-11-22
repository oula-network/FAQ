---
cover: ../.gitbook/assets/Mining Configuration Q&A.jpg
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

# ⚙️ Mining Configuration Q\&A

{% embed url="https://oula.network/en/" %}

**Q: How to add a mining machine and set up miner account? How to enter the miner management backend?**

A: Please refer to the [<mark style="color:blue;">**Aleo Mining Tutorial**</mark>](../start-mining/publish-your-docs-1.md). For new Oula users, please refer to detailed Beginner's Guide.

***

**Q: What does the "PLIMIT too low" error in HiveOS mean? How can it be resolved?**

**A:** The "PLIMIT too low" error indicates that the power limit setting for the GPU is too low, which may prevent mining software from starting. To resolve this issue, follow these troubleshooting and adjustment steps:

1. Check if a power limit has been set for the GPU. If it has, either remove the setting or adjust it to a reasonable range. (For detailed adjustment steps, refer to the official documentation under [_Overclocking Nvidia GPUs_](https://hiveon.com/knowledge-base/getting\_started/start\_oc/#creating-an-overclocking-template).)
2. If no power limit has been set, verify that the power supply is sufficient to support multiple GPUs, as insufficient power may prevent the system from starting.
3. Ensure that the system is not running other high-load applications simultaneously, as this may further reduce available power and affect the stability of the mining operation.

***

**Q: Why do multiple mining machine work but only one worker shows as online?**

A: If multiple workers use the same worker-name, the system will display the combined power. To display the power separately, please set a unique worker-name for each mining machine.

***

**Q: How to resolve CUDA-related errors in Aleo mining software?**

A: Please follow the bellow steps:\
1\)  Reinstall the software and use the recommended **CUDA version**. (Requirements will be updated when a new CUDA version is released)\
2\) Insufficient VRAM: Replace the graphics card.

***

**Q: How to fix the ‘unable to connect operation’ error in Aleo mining software?**

A: Please check if the worker could properly connect to the mining pool server address.

***

**Q: The log in cat prover.log shows mining power without ‘found’ message, and the mining pool end does not display worker information, how to solve it?**

A: This may be due to insufficient power from a single machine to generate a valid solution.

{% hint style="info" %}
Suggestions:

* Extend the observation time
* Check if the network is stable
{% endhint %}

***

**Q: I set up the configuration according to the Aleo mining tutorial, but the mining software shows ‘GPU and CPU not found’. How to solve it?**

A: Please check if the graphics card drivers are correctly installed, or confirm if your graphics card is an Nvidia model.

***

**Q: How do I resolve the error "nohup: failed to run command '/home/user/aleo-prover-cuda': Permission denied" in Aleo mining software?**

A: Please execute <mark style="color:red;">`chmod +x oula-pool-prover`</mark> to add execution permissions for the Prover.

***

**Q: How can I fix the issue “Error aleo\_prover::client: Connection closed: stream closed from Prover”?**\
A: If this issue occurs repeatedly, please check your network connection and ensure the mining pool server is functioning properly. If it happens occasionally, please ignore it.

***

**Q: On Ubuntu 22.04, the default GCC version is 9.4. How do I upgrade to 11.4?**\
A: Follow these steps:

1.  Upgrade to gcc-11 and g++-11:

    ```bash
    apt install software-properties-common
    add-apt-repository ppa:ubuntu-toolchain-r/test
    apt update
    apt install gcc-11 g++-11
    ```
2.  Adjust the default gcc and g++ priority:

    ```bash
    update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-11 10
    update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-11 10
    ```

***

**Q: What does the error “error while loading shared libraries: libnvrtc.so.12: cannot open shared object file: No such file or directory” mean?**\
A: This indicates an issue with your CUDA installation. Please check if CUDA is installed correctly.

***

**Q: How do I check the system’s GCC version?**\
A: Execute the following command to check the system's GCC version.

```bash
gcc --version
```





[**Back to Oula**](https://oula.network/en/login)
