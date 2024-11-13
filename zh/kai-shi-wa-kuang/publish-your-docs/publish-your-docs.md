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

# 介紹

{% embed url="https://oula.network/zh/" %}

## 介紹

Autonomys-farmer 包含以下[組件](https://github.com/oula-network/autonomys/releases)：

* `autonomys-controller` 負責代理 node rpc，用於管理集群組件
* `sharded-cache` piece 分片緩存
* `full-piece-sharded-cache` piece 分片緩存全量節點
* `proof-server` GPU 出塊，用於計算 proof
* `plot-server` plotting 服務，用於encode 數據
* `plot-client` farming 組件，用於掃盤以及提交 solution

### 架構

目前所有的集群管理都是基於 nats 來做的，但是 cache 的具體數據傳輸是通過 TCP 做 p2p 傳輸。

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>





[**返回Oula**](https://oula.network/zh/login)
