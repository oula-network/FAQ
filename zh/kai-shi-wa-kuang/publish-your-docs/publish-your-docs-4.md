---
cover: ../../.gitbook/assets/aa.png
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

# 👨‍🔧 Autonomys Piece 轉換工具

{% embed url="https://oula.network/zh/" %}

### Autonomys Piece 轉換工具

可以將 `autonomys-node` 同步後的數據轉換為 `piece` 快取資料，請按照以下步驟導出 `piece` 快取資料：

1.  使用命令：

    ```bash
    NODE_URL="http://192.168.1.1:9944" ./autonomys-export-piece
    ```
2. 運行指令後，生成的 `piece` 資料會自動儲存至本機的 `full-cache-tmp` 資料夾。
3. 在使用 `autonomys-full-piece` 組件時，將 `path` 參數指定為該目錄即可。

{% hint style="warning" %}
`NODE_URL` 中指定的 `autonomys-node` 啟動指令必須包含 `--sync=full` 參數。
{% endhint %}

### Autonomys Piece 驗證工具

可以驗證已生成的 `piece` 資料，運行以下指令即可驗證：

{% code overflow="wrap" %}
```bash
./autonomys-farmer util verify-piece --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.3:4222
```
{% endcode %}

### 快速下載節點數據

可以從百度網盤下載預先同步好的 `node` 資料，檔案名稱為 `node-db.tar.gz`。下載並解壓縮後，您仍需同步最新的節點數據，但會大幅縮短同步時間。

<mark style="color:red;">**數據更新至新加坡時間 2024 年 11 月 12 日 23 點**</mark>

{% hint style="warning" %}
這是原始的 `node` 資料，還需要使用 `autonomys-export-piece` 工具將其轉換為 `piece` 資料，才能進行封裝使用。
{% endhint %}

**下載連結**: [https://pan.baidu.com/s/105H1EOrnfA9hcpcU265RcA](https://pan.baidu.com/s/105H1EOrnfA9hcpcU265RcA)\
**提取碼**: 67nq





[**返回Oula**](https://oula.network/zh/login)
