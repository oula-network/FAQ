---
cover: ../.gitbook/assets/挖礦設置相關問題.jpg
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

# ⚙️ 挖礦設置相關問題

{% embed url="https://oula.network/zh/" %}

**Q: 如何添加礦工並設置礦工號？如何進入礦機管理後台？**

A: 請參閱 Oula 新手教程，詳細步驟請訪問[Aleo挖礦教程](../kai-shi-wa-kuang/publish-your-docs.md)。



**Q: HiveOS顯示「PLIMIT過低」，這是什麼意思？如何解決？**

A：「PLIMIT過低」表示GPU的功率限制設置過低，可能會影響挖礦軟件的啟動。要解決此問題，可以根據以下步驟進行排查與調整：&#x20;

1\. 檢查GPU是否設置了功率限制，若已設置，請取消該設定或調整至合理範圍。 （具體調整步驟可參考官方文檔中的[Overclocking Nvidia GPUs](https://hiveon.com/knowledge-base/getting\_started/start\_oc/#creating-an-overclocking-template)）

2\. 若未設置功率限制，請確認電源的功率是否足夠支持多顆GPU的運行，避免電力不足導致系統無法啟動。&#x20;

3\. 確認系統是否同時運行其他高負載應用程序，這可能會進一步降低可用的功率，影響挖礦運行的穩定性。



**Q: 如何監控礦機並獲取離線警報推送？**

A: 目前平台尚不支持此功能，未來會陸續開發中。您可以通過 Prover 本地接口進行自我監控。



**Q: 為什麼多台礦機工作但只顯示一台機器在線？**

A: 若多台礦機使用相同的 worker-name，系統會將算力合併顯示。若要分開顯示算力，請為每台礦機設置唯一的 worker-name。



**Q: Aleo Miner 挖礦軟體反饋 Cuda 相關錯誤，如何解決？**

A: 请根据以下步骤进行操作：\
1）請重新安裝軟體，並使用推薦的 **CUDA 版本**；（新的 CUDA 版本發布後會更新相關要求）\
2）顯存容量不足：更換顯示卡。



**Q: Aleo Miner 挖礦軟體提示 “unable to connect operation” 錯誤，如何解決？**

A: 請檢查礦機是否能正常連接到礦池伺服器地址。



**Q: 在 **<mark style="color:red;">**cat prover.log**</mark>** 日誌中顯示有算力但沒有出現 “found” 字樣，礦池端也沒有顯示礦機信息，該如何解決？**

A: 可能是單台機器的算力太低，無法生成有效的 solution。

{% hint style="info" %}
建議：

1）延長觀察時間；&#x20;

2）檢查網絡是否穩定
{% endhint %}



**Q: 我按照 Aleo 挖礦教程完成配置，但挖礦軟體顯示“沒有找到 GPU 和 CPU”，應該如何解決？**

A: 請檢查顯卡驅動是否正確安裝，或者確認您的顯卡是否為 Nvidia 型號。



**Q: Aleo Miner 軟體提示 “nohup: failed to run command '/home/user/aleo-prover-cuda': Permission denied”，如何解決？**

A: 請執行 <mark style="color:red;">`chmod +x oula-pool-prover`</mark> 為 Prover 添加可執行權限。



**Q: 如何修復“錯誤 aleo\_prover::client: 連接斷開: 來自 Prover 的流已關閉”這個問題？**\
A: 如果這個問題反覆出現，請檢查自己的網絡連接和礦池服務端的狀況是否正常。如果只是偶爾出現一次，可以先忽略。



**Q: 在 Ubuntu 22.04 上，默認 GCC 版本是 9.4，如何升級到 11.4？**\
A: 可以參考以下步驟：

1.  升級 gcc-11 和 g++-11：

    ```bash
    apt install software-properties-common
    add-apt-repository ppa:ubuntu-toolchain-r/test
    apt update
    apt install gcc-11 g++-11
    ```
2.  調整默認 gcc 和 g++ 的優先級：

    ```bash
    update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-11 10
    update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-11 10
    ```



**Q: “error while loading shared libraries: libnvrtc.so.12: cannot open shared object file: No such file or directory” 這個報錯是什麼問題？**\
A: 這代表著 CUDA 安裝問題，請檢查 CUDA 是否正確安裝。



**Q: 如何查看系統 GCC 版本？**\
A: 执行以下命令查看系統的 GCC 版本。

```bash
gcc --version
```





[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
