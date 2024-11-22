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

# 💡 Recommended Software and Hardware Configuration

{% hint style="info" %}
This software is only supported on Linux operating systems and Nvidia GPU environments.
{% endhint %}

### **Operating System and Dependency Software**

* **Operating System**: Ubuntu 22.04
* **GPU Driver Version**: ≥ 525.60.13, or alternatively, install **CUDA 12.4** directly.
* **File System**: Ext4
* **Supervisor**: 4
* **NATS Server**: v2.10.22
* **numactl**: Required for managing NUMA (Non-Uniform Memory Access) nodes

### Recommended Server Configuration

<table data-view="cards"><thead><tr><th>Server</th><th>CPU</th><th>MEM</th><th>GPU</th><th>SSD</th><th>Ethernet</th><th>Running Components</th></tr></thead><tbody><tr><td>Node</td><td>64 cores</td><td>64GB / 128GB</td><td>Required</td><td>500GiB</td><td>at least 1 Gbps</td><td><p><code>controller</code> </p><p><code>autonomys-node</code> </p><p><code>proof-server</code> </p><p><code>nats-server</code></p></td></tr><tr><td>Plotter</td><td>at least 30 cores per GPU</td><td>at least 64GB per GPU</td><td>Required</td><td>at least <strong>1 TiB</strong> for caching plot data</td><td>at least 20 Gbps</td><td><p><code>plot-server</code> </p><p><code>sharded-cache</code> </p><p><code>full-piece-cache</code></p></td></tr><tr><td>Storage</td><td>depending on the storage capacity</td><td>depending on the storage capacity</td><td>Not Required</td><td>depending on the storage capacity</td><td>at least 20 Gbps</td><td><code>plot-client</code></td></tr></tbody></table>



