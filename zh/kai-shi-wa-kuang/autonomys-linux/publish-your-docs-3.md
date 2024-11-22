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

# 附錄

{% embed url="https://oula.network/zh/" %}

## 附錄

### 使用命令

手動初始化集群，執行後會在n秒後重新初始化整個集群

```sh
autonomys-farmer util \
reinitialization-cache \
    --nats-servers nats://192.168.200.6:4222 \
    --delay 0
```

• `--delay 0`：初始化延遲，單位：秒

模擬 plot 的 download sector 過程，對 cache cluster 發起請求，檢查集群狀態

```sh
autonomys-farmer util \
sharded-cache-benchmark \
    --nats-servers nats://192.168.0.2:4222 \
    --sectors 256 \
    --epoch 1 \
    --cache-item-type split-parity-piece
```





[**返回Oula**](https://oula.network/zh/login)
