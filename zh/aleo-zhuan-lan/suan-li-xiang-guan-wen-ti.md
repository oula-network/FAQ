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

# ⚡ 算力相關問題

{% embed url="https://oula.network/zh" %}

**Q: Aleo 挖礦中，算力單位如何理解？**

A: 在 Aleo 挖礦中，算力單位包括以下幾個：

* **p** 代表 Proof
* **c** 代表 Commitment
* **h** 代表 Hashrate
* **s** 代表 Solution

這些單位在每秒的測量中是等價的，即 p/s、s/s、c/s、h/s 都表示每秒的算力。



**Q: Aleo 挖礦一般多久會顯示出算力？**

A: 通常會在十分鐘內顯示出算力。



**Q: 為什麼我的 Aleo 礦機突然算力變低？**

A: 每個 Epoch 都有自身的難度系數，因此算力會根據難度變化而波動，這是正常現象。



**Q: 為什麼我新加入的 Aleo 礦機算力非常小？**

A: 新加入礦池後，需要等待礦機穩定運行約十五分鐘再進行觀察。由於 Epoch 难度的變化，算力可能會波動，建議延長觀察時間。



**Q: 為什麼啟動礦機時總有一張顯卡的算力明顯低於其他顯卡？**

A: 請檢查顯卡型號是否一致，確保礦機電壓穩定，並檢查是否有其他進程佔用該顯卡。



**Q: 如何查看顯卡驅動是否正常安裝？**

A: 執行 <mark style="color:red;">`nvidia-smi`</mark> 命令後，操作成功時會顯示如下信息。您可以從返回的結果中查看 GPU 版本及運行狀況。

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



**Q: 運行挖礦軟體時發生死機該怎麼辦？**

A: 死機問題可能由多種原因造成，如電壓或硬件問題。如果自行排查後無法找到問題，建議上傳或截圖系統日誌，並在 Oula 社群聯繫管理員協助查看。



**Q: 為什麼在挖掘 Aleo 時礦機顯示離線？**

A: 若平台顯示礦機離線，但日誌正常且每個 Epoch 收益正常，則可能是網絡問題導致暫時無法推送礦機數據，但不影響收益。查看日誌，請執行 <mark style="color:red;">`tail -f prover.log`</mark>命令。



[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
