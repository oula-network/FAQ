---
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

# 🤖 Aleo挖礦教程 - Pool

{% embed url="https://oula.network/zh" %}

> &#x20;❕ [ALEO](https://www.aleo.org/)是一個融合PoW和PoS共識機制的區塊鏈項目，旨在提供高度隱私的智能合約功能。其利用先進的Synthesis Puzzle技術來確保交易的隱私和安全性。ALEO專注於構建去中心化應用程序，提供高效且安全的隱私保護方案。



請詳細閱讀挖礦教程，並按照步驟完成礦機接入礦池的操作。

### 環境準備

* **操作系統：**Ubuntu 22.04 (GCC 11.4)
* **GPU CUDA版本:** 12.3
* **軟體客戶端：**[Oula-Aleo](https://github.com/oula-network/aleo/releases)

{% hint style="info" %}
請隨時關注[OULA官方網站](https://oula.network/zh)公告，並更新使用最新版本的軟體客戶端，以獲得更優質的技術服務和更高的 Token 產出。
{% endhint %}

### 帳號設立

* 須通過完成 [OULA帳號註冊](https://oula.network/zh/register)，在用戶面板→礦池市場→[子帳戶管理](https://oula.network/zh/pool/manager?tab=subAccount)模組下，使用 Aleo 對應的預設或新建立的子帳戶名啟動軟體。
* 運行軟體客戶端後，每日的產出將自動累計至對應的子帳戶中。餘額達到最低起付金額後，平台將每日自動支付至綁定的提現地址。

### 程序運行

#### **Aleo Pool Prover**

* 在Ubuntu系統中，下載並解壓縮[aleo-pool-prover](https://github.com/oula-network/aleo/releases)
* 設置執行程序的權限命令

```sh
chmod +x aleo-pool-prover
```

* 設置參數對應的文本資訊，執行程序啟動命令

{% code overflow="wrap" %}
```bash
nohup ./aleo-pool-prover --pool wss://aleo.oula.network:6666 --account account --worker-name worker_name > prover.log 2>&1 &
```
{% endcode %}

* [ ] 替換礦池地址（--pool）：以[**概覽**](https://oula.network/zh/pool/manager)頁提供的「**礦池地址**」為準
* [ ] 替換帳戶（--account）：[**子賬戶管理**](https://oula.network/zh/pool/manager?tab=subAccount)頁已創建的「**賬戶名**」
* [ ] 替換設備名（--worker-name）：礦工名稱

{% hint style="warning" %}
子帳戶和礦工名稱可自訂義，需滿足全域唯一性！&#x20;

建議使用2-15個小寫字母、數字或其組合，且不能以數字開頭。
{% endhint %}

* 執行查看日誌命令

```bash
tail -f prover.log
```

{% hint style="success" %}
若在<mark style="color:red;">`prover.log`</mark>中見到相關成功訊息，則表示程序已成功啟動。
{% endhint %}

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
如果您不需要輸出日誌內容，可以將啟動命令中的“&> prover.log &”替換為“> /dev/null 2>&1 &”。
{% endhint %}

* 執行程式停止命令

```bash
killall aleo-pool-prover
# 強制執行
```

### 礦機監控及產出查看

設備穩定運行並提交數據後，在用戶面板→礦池市場→[礦工管理](http://192.168.1.51/zh/pool/manager?tab=miner)和[產出/支付](http://192.168.1.51/zh/pool/manager?tab=output)模組下，切換對應的子賬戶即可檢視礦工運行狀態、產出詳情及支付詳情。





[**返回Oula**](https://oula.network/zh/login)
