---
hidden: true
cover: ../.gitbook/assets/中文.jpg
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

# 🤖 Autonomys挖礦教程 - Linux

{% embed url="https://oula.network/zh/" %}

{% hint style="info" %}
請詳細閱讀Farmer部署文檔，並按照步驟完成礦機部署操作。
{% endhint %}

## 介绍

farmer 包含以下组件：

* `autonomys-controller` 负责代理 node rpc，管理集群组件
* `sharded-cache` piece 分片缓存
* `full-piece-sharded-cache` piece 分片缓存全量节点
* `proof-server` GPU 出块，计算 proof
* `plot-server` plotting 服务，encode 数据
* `plot-client` farming 组件，用于扫盘以及提交 solution

### 架构

目前所有的集群管理都是基于 nats 来做的，但是 cache 的具体数据传输是通过 TCP 做 p2p 传输

### 软件和硬件环境建议配置

{% hint style="warning" %}
仅支持 Linux 操作系统，以及 Nvidia GPU 硬件
{% endhint %}

#### 操作系统及依赖软件

* Ubuntu 22.04
* GPU 驱动版本 ≥ 525.60.13 或者直接安装 cuda 12.4
* 文件系统 Ext4
* Supervisor 4
* Nats-server v2.10.22
* numactl

#### 服务器建议配置

<table><thead><tr><th width="97">类别</th><th width="105">CPU</th><th width="99">内存</th><th width="85">GPU</th><th width="112">SSD</th><th width="116">网络</th><th width="181">运行组件</th></tr></thead><tbody><tr><td>节点机</td><td>64核</td><td>64G/128G</td><td>需要</td><td>500GiB</td><td>千兆网卡</td><td><code>controller</code> <code>autonomys-node</code> <code>proof-server</code> <code>nats-server</code></td></tr><tr><td>P 盘机</td><td>每个GPU需要30核</td><td>每个GPU需要 64 G</td><td>需要</td><td>20GiB 用于缓存 plot 数据</td><td>万兆网卡*2</td><td><code>plot-server</code> <code>sharded-cache</code> <code>full-piece-cache</code></td></tr><tr><td>存储机</td><td>取决于存储容量</td><td>取决于存储容量</td><td>不需要</td><td>取决于存储容量</td><td>万兆网卡*2</td><td><code>plot-client</code></td></tr></tbody></table>

####

#### 最佳实践

{% hint style="info" %}
_以下名称 IP 等都是示例_
{% endhint %}

#### 环境介绍

<table><thead><tr><th width="107">列别</th><th width="118">ip 地址</th><th width="158">配置</th><th width="382">部署组件</th></tr></thead><tbody><tr><td>节点机1</td><td>192.168.1.1</td><td>GPU*1</td><td><code>controller</code> <code>autonomys-node</code> <code>proof-server</code> <code>nats-server</code></td></tr><tr><td>节点机2</td><td>192.168.1.2</td><td>GPU*1</td><td><code>controller</code> <code>autonomys-node</code> <code>proof-server</code> <code>nats-server</code></td></tr><tr><td>节点机3</td><td>192.168.1.3</td><td>GPU*1</td><td><code>controller</code> <code>autonomys-node</code> <code>proof-server</code> <code>nats-server</code></td></tr><tr><td>P 盘机1</td><td>192.168.1.4</td><td>GPU*4</td><td><code>autonomys-plot-server-0</code> <code>autonomys-plot-server-1</code> <code>autonomys-plot-server-2</code> <code>autonomys-plot-server-3</code> <code>sharded-cache</code> <code>full-piece-cache</code></td></tr><tr><td>P 盘机2</td><td>192.168.1.5</td><td>GPU*4</td><td><code>autonomys-plot-server-0</code> <code>autonomys-plot-server-1</code> <code>autonomys-plot-server-2</code> <code>autonomys-plot-server-3</code> <code>sharded-cache</code> <code>full-piece-cache</code></td></tr><tr><td>存储机1</td><td>192.168.1.6</td><td>8T NVMe*4 <code>/mnt/nvme0n1</code> <code>/mnt/nvme0n2</code> <code>/mnt/nvme1n2</code> <code>/mnt/nvme1n1</code></td><td><code>autonomys-plot-client</code></td></tr><tr><td>存储机2</td><td>192.168.1.7</td><td>8T NVMe*4 <code>/mnt/nvme0n1</code> <code>/mnt/nvme0n2</code> <code>/mnt/nvme1n1</code> <code>/mnt/nvme1n2</code></td><td><code>autonomys-plot-client</code></td></tr></tbody></table>

#### Supervisor 配置

#### **节点机配置**

> 需要部署4個組件：`controller`，`autonomys-node`，`proof-server``和nats-server`&#x20;
>
> 部署顺序：`nats-server` -> `autonomys-node` -> `controller` -> `proof-server`&#x20;

* **nats-server**

{% code overflow="wrap" %}
```ini
# 节点机1 上的 nats-server 配置，节点机1作为 nats-server 种子服务器
# /etc/supervisor/conf.d/nats-server.conf

[program:nats-server]
command=/root/subspace/nats-server -p 4222 --jetstream --store_dir /var/nats-server -cluster nats://0.0.0.0:4248 --cluster_name ns-cluster
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/nats-server.log
```
{% endcode %}

{% code overflow="wrap" %}
```ini
# 节点机2 nats-server 配置
# /etc/supervisor/conf.d/nats-server.conf

[program:nats-server]
command=/root/subspace/nats-server -p 4222 --jetstream --store_dir /var/nats-server -cluster nats://0.0.0.0:4248 -routes nats://192.168.1.1:4248 --cluster_name ns-cluster
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/nats-server.log
```
{% endcode %}

{% hint style="info" %}
nats-server 的参数可以参考[文档](https://docs.nats.io/running-a-nats-service/configuration/clustering)
{% endhint %}

* **autonomys-controller**

{% code overflow="wrap" %}
```ini
[program:subspace-controller]
command=/root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 controller --tmp --node-rpc-url ws://10.30.1.2:9944
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-controller.log
```
{% endcode %}

* **autonomys-node**

{% code overflow="wrap" %}
```ini
# autonomys-node 配置
# /etc/supervisor/conf.d/autonomys-node.conf

[program:autonomys-node]
command=/root/subspace/autonomys-node run --base-path /var/subspace-node --farmer --rpc-listen-on 0.0.0.0:9944 --chain taurus --sync full --rpc-methods unsafe --rpc-cors all
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-node.log
```
{% endcode %}

* **autonomys-proof-server**

{% code overflow="wrap" %}
```ini
[program:autonomys-proof-server]
command=/root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 proof-server
autorestart=true
user=root
environment=CUDA_VISIBLE_DEVICES=0
redirect_stderr=true
stdout_logfile_maxbytes=500MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-proof-server.log
```
{% endcode %}

启动命令参数及环境变量解释：

* \--nats-server 参数指定 nats 服务器地址
* `CUDA_VISIBLE_DEVICES` 环境变量可以指定 GPU，0 表示 GPU0，1 表示GPU1，以此类推

**存储机配置(以 4 盘为例)**

**autonomys-plot-client**

{% code overflow="wrap" %}
```ini
# autonomys-plot-client 配置
# /etc/supervisor/conf.d/autonomys-plot-client.conf

[program:autonomys-plot-client]
command=/root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 plot-client path=/mnt/nvme0n1/,sectors=8000  path=/mnt/nvme0n2/,sectors=8000 path=/mnt/nvme1n0/,sectors=8000 path=/mnt/nvme1n1/,sectors=8000
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-plot-client.log
```
{% endcode %}

启动命令参数解释：

* \--nats-server 参数指定 nats 服务器地址
* path=/path/to/plot-dir，sectors=8000 指定 plot 文件路径以及 plot 的扇区数量

**P 盘机配置 (以 4 GPU为例)**

> P需要部署3 个组件：`autonomys-plot-server` ，`autonomys-sharded-cache`和`autonomys-full-piece-cache`&#x20;
>
> `autonomys-plot-server` 从 `autonomys-sharded-cache`, `autonomys-full-piece-cache` 获取 piece 用于 p 盘

**autonomys-sharded-cache**

{% code overflow="wrap" %}
```ini
# sharded-cache 配置
# /etc/supervisor/conf.d/autonomys-sharded-cache.conf

[program:autonomys-sharded-cache]
command=/root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 sharded-cache path=/var/autonomys-sharded-cache
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-sharded-cache.log
```
{% endcode %}

启动命令参数解释：

* \--nats-server 参数指定 nats 服务器地址
* path=/path/to/autonomys-sharded-cache 用于指定 piece 缓存存储路径

**autonomys-full-piece**

{% code overflow="wrap" %}
```ini
# autonomys-full-piece 配置
# /etc/supervisor/conf.d/autonomys-full-piece.conf

[program:autonomys-full-piece]
command=/root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 full-piece-sharded-cache --priority-queue --tmp path=/var/autonomys-full-piece
autorestart=true
user=root
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-full-piece.log
```
{% endcode %}

启动命令参数解释：

* \--nats-server 参数指定 nats 服务器地址
* path=/path/to/autonomys-full-piece 参数指定 full-piece 存储路径

**autonomys-plot-server**

{% code overflow="wrap" %}
```ini
# autonomys-plot-server 配置文件
# /etc/supervisor/conf.d/autonomys-plot-server.conf

[group:autonomys-plot-server]
programs=autonomys-plot-server-0,autonomys-plot-server-1,autonomys-plot-server-2,autonomys-plot-server-3
[program:autonomys-plot-server-0]
command=numactl -C 0-31 -l /root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 plot-server --priority-cache --listen-port 9966 /var/plot-server/base-path-0
autorestart=true
user=root
environment=CUDA_VISIBLE_DEVICES=0
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/subspace-plotter-0.log

[program:autonomys-plot-server-1]
command=numactl -C 96-127 -l /root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 plot-server --priority-cache --listen-port 9967 /var/plot-server/base-path-1
autorestart=true
user=root
environment=CUDA_VISIBLE_DEVICES=1
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-plotter-1.log

[program:autonomys-plot-server-2]
command=numactl -C 96-127 -l /root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 plot-server --priority-cache --listen-port 9968 /var/plot-server/base-path-2
autorestart=true
user=root
environment=CUDA_VISIBLE_DEVICES=2
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-plotter-2.log

[program:autonomys-plot-server-3]
command=numactl -C 144-175 -l /root/subspace/autonomys-farmer cluster --nats-server nats://192.168.1.1:4222 --nats-server nats://192.168.1.2:4222 --nats-server nats://192.168.1.2:4222 plot-server --priority-cache --listen-port 9969 /var/plot-server/base-path-3
autorestart=true
user=root
environment=CUDA_VISIBLE_DEVICES=3
redirect_stderr=true
stdout_logfile_maxbytes=100MB
stdout_logfile_backups=2
stdout_logfile=/var/log/autonomys-plotter-3.log
```
{% endcode %}

启动命令参数及环境变量解释：

* \--nats-server 参数指定 nats 服务器地址
* `CUDA_VISIBLE_DEVICES` 指定 GPU, 0 表示 GPU0, 1 表示GPU1, 以此类推。
* `GPU_CONCURRENCY` 增大此值会提高显存使用量，在使用不同型号的 GPU 时，可以考虑适当调整该变量。

{% hint style="danger" %}
需要注意的是， 使用 numactl 工具绑定 CPU 核心时，需要考虑 GPU 的 numa 亲和性以达到最佳性能。

使用 `nvidia-smi topo -m` 命令查看 GPU numa 亲和性。
{% endhint %}

{% code overflow="wrap" %}
```bash
# nvidia-smi topo -m
        GPU0    GPU1    NIC0    NIC1    CPU Affinity    NUMA Affinity   GPU NUMA ID
GPU0     X      SYS     NODE    NODE    0-47,96-143     0               N/A
GPU1     X      SYS     NODE    NODE    0-47,96-143     0               N/A
GPU2    SYS      X      SYS     SYS     48-95,144-191   1               N/A
GPU3    SYS      X      SYS     SYS     48-95,144-191   1               N/A
NIC0    NODE    SYS      X      PIX
NIC1    NODE    SYS     PIX      X

Legend:

  X    = Self
  SYS  = Connection traversing PCIe as well as the SMP interconnect between NUMA nodes (e.g., QPI/UPI)
  NODE = Connection traversing PCIe as well as the interconnect between PCIe Host Bridges within a NUMA node
  PHB  = Connection traversing PCIe as well as a PCIe Host Bridge (typically the CPU)
  PXB  = Connection traversing multiple PCIe bridges (without traversing the PCIe Host Bridge)
  PIX  = Connection traversing at most a single PCIe bridge
  NV#  = Connection traversing a bonded set of # NVLinks

NIC Legend:

  NIC0: mlx5_0
  NIC1: mlx5_1
```
{% endcode %}

### 附录

#### 使用命令

手動执行以下命令，会在n秒后重新初始化整个集群

{% code overflow="wrap" %}
```sh
subspace-farmer util \
reinitialization-cache \
    --nats-servers nats://192.168.200.6:4222 \
    --delay 0
```
{% endcode %}

• --delay 0: 初始化延迟，单位：秒

模拟 plot 的 download sector 过程，对 cache cluster 发起请求，检查集群状态

{% code overflow="wrap" %}
```sh
subspace-farmer util \
sharded-cache-benchmark \
    --nats-servers nats://192.168.0.2:4222 \
    --sectors 256 \
    --epoch 1 \
    --cache-item-type split-parity-piece
```
{% endcode %}



[**返回Oula**](https://oula.network/zh/login)
