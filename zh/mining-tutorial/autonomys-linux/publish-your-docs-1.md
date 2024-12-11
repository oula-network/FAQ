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
    visible: true
  pagination:
    visible: true
---

# 💡 軟件和硬件環境建議配置

{% embed url="https://oula.network/zh/" %}

## 軟件和硬件環境建議配置

本軟件僅支持 Linux 操作系統，以及 Nvidia GPU 環境。

### 操作系統及依賴軟件

* Ubuntu 22.04
* GPU 驅動版本 ≥ 525.60.13 ，或者直接安裝 cuda 12.4
* 文件系統 Ext4
* Supervisor 4
* Nats-server v2.10.22
* numactl

### 服務器建議配置

<table data-view="cards"><thead><tr><th>類別</th><th>CPU</th><th>內存</th><th>GPU</th><th>SSD</th><th>網絡</th><th>運行組件</th></tr></thead><tbody><tr><td>節點機</td><td>64核</td><td>64G/128G</td><td>需要</td><td>500GiB</td><td>千兆網卡</td><td><p><code>controller</code> </p><p><code>autonomys-node</code> </p><p><code>proof-server</code> </p><p><code>nats-server</code></p></td></tr><tr><td>P 盤機</td><td>每張GPU需要30核</td><td>每張GPU需要 64G</td><td>需要</td><td>1 TiB 用於緩存 plot 數據</td><td>萬兆網卡</td><td><p><code>plot-server</code> </p><p><code>sharded-cache</code> </p><p><code>full-piece-cache</code></p></td></tr><tr><td>存儲機</td><td>取決於存儲容量</td><td>取決於存儲容量</td><td>不需要</td><td>取決於存儲容量</td><td>萬兆網卡</td><td><code>plot-client</code></td></tr></tbody></table>





[**返回Oula**](https://oula.network/zh/login)
