---
cover: ../.gitbook/assets/Frame 427318688.png
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

{% embed url="https://oula.network/zh" %}

**Q: 如何添加礦工並設置礦工號？如何進入礦機管理後台？**

A: 請參閱 Oula 新手教程，詳細步驟請訪問[Aleo挖礦教程](../kai-shi-wa-kuang/publish-your-docs.md)。



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

A: 請執行 <mark style="color:red;">`chmod +x aleo-prover-cuda`</mark> 為 Prover 添加可執行權限。





[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
