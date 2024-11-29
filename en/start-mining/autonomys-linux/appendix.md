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

# Appendix

## Appendix

### **Using the Command**

Execute the command to manually initialize the cluster. The entire cluster will be reinitialized after **n** seconds.

```sh
autonomys-farmer util \
reinitialization-cache \
    --nats-servers nats://192.168.200.6:4222 \
    --delay 0
```

• `--delay 0`: Initialization delay, in seconds.

Simulate the **plot download sector** process by sending requests to the cache cluster and checking the cluster status.

```sh
autonomys-farmer util \
sharded-cache-benchmark \
    --nats-servers nats://192.168.0.2:4222 \
    --sectors 256 \
    --epoch 1 \
    --cache-item-type split-parity-piece
```



