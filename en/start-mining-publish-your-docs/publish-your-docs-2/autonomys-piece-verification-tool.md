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
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ✔️ Piece Verification Tool

### Autonomys Piece Verification Tool

The Autonomys Piece Verification Tool allows you to verify generated `piece` data. Run the following command to initiate verification:

{% code overflow="wrap" %}
```bash
./autonomys-farmer util verify-piece --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.3:4222
```
{% endcode %}



