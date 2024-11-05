---
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

# 🖥️ 礦機相關問題

{% embed url="https://oula.network/zh/" %}

#### **Q: tSSC 與 AI3 的轉換比率是多少？**

**A:** 完整的代幣經濟學將於2024年11月13日公開。

根據不同的激勳階段，會有不同的獎勳池和機制，因此不存在統一的 tSSC 至 AI3 的轉換比率，具體的計算方法請參閱[自述文件](https://github.com/subspace/incentivized-testnets)。

***

#### **Q: Autonomys須使用哪種錢包？**

**A: 建議**使用 **Subwallet** 錢包，詳細設置指南請參考：[Subwallet 安裝指南](https://docs.autonomys.xyz/wallets/subwallet/)。

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=Gsjfxhnw-1w" %}

***

#### **Q: AI3 的最大供應量是多少？**

**A:**\
z最大供應量為 **10 億枚**，該數量將在主網上線後逐步釋放。

***

#### **Q: 關於 Autonomys（Subspace）專案的使用者注意事項有哪些？**

**A:**

1. 主網啟動後，將首先進行主網數據的準備和同步，然後才能開始 P 盤（plotting）過程。
2. 主網發佈後，專案方會為全網準備數據並留出 P 盤的時間，因此參與者無法提前啟動挖礦，最多只能在主網啟動後的 P 盤窗口期內增加 P 盤數量。
3. P 盤的硬盤數據有時效性，需要定期重新封裝。
4. P 盤可使用 CPU 或 GPU 計算，然而 GPU 在效率和資源消耗上明顯優於 CPU。
5. 存儲設備需要使用 **SSD**（具備高速隨機讀取能力）。若使用 HDD，單個硬盤最多僅能承載約 200GB 的數據，因此目前 HDD 無法有效參與挖礦。
6. 主網發佈後，將分為兩期進行，只有在主網第二期啟動後才可進行代幣交易。

***

#### **Q: 抽水百分比是多少？**

**A:**\
抽水百分比將於主網啟動後公佈。

***

#### **Q: 什麼是過期數據？**

**A:**\
為了讓 Farmer 儲存用戶上傳的新數據並平衡數據分片，數據需要不斷重 P 盤。過期數據指的是那些未更新或重新封裝的數據，這些數據會被視為過期，並需重新進行 P 盤操作。

***

#### **Q: 計算算力的邏輯是什麼？使用的單位是什麼？**

**A:**\
算力與存儲空間大小正相關，因此算力的單位為 **MiB**。即每單位 MiB 存儲空間對應相應的算力。

***

#### **Q: 如何查詢官方鏈上數據？**

**A:**\
官方鏈上數據可以通過以下鏈上瀏覽器進行查詢：[Astral Explorer](https://astral.autonomys.xyz/)。

***

#### **Q: 進行 P 盤時應使用 GPU 還是 CPU？**

**A:**\
P 盤計算可使用 **CPU** 或 **GPU**，但 GPU 在效率上顯著優於 CPU，能更快地完成計算並減少資源消耗。

***

#### **Q: 是否為 GPU 還是硬件（存儲）類型的挖礦？**

**A:**\
挖礦至少需要搭配 **GPU/CPU** 和 **硬件存儲**。儲存是關鍵，且需要使用快速讀寫的存儲設備，如 SSD。

***

#### **Q: 當前的帶寬需求是多少？**

**A:**\
存儲伺服器需至少具備 **20 Gbps** 的帶寬，而每個節點（Node）則需要至少 **200 Mbps** 的帶寬。

***

#### **Q: 可以使用哪些顯卡進行挖礦？支持哪些系列的顯卡？是否支持 AI 卡和企業級 Nvidia 顯卡？**

**A:**\
Oula 的挖礦軟體理論上支持 **Nvidia 2080 系列及以上** 顯卡進行挖礦。AI 卡和企業級 Nvidia 顯卡理論上也應該是支持的，但具體性能表現需根據實際情況來確定。

***

#### **Q: 挖礦所需的最低硬件配置是什麼？**

**A:**\
最低硬件配置需求為：

* **CPU**: 至少 4 核心
* **內存（MEM）**: 至少 8GB
* **顯卡（GPU）**: Nvidia 2080 系列及以上
* **存儲（SSD）**: 至少 1TB SSD，且需支持高效隨機讀寫操作。

***

#### **Q: 是否支持在 WSL 系統中挖礦？**

**A:**\
目前，Oula 的挖礦軟體僅支持 **Linux 系統**，不支持在 Windows Subsystem for Linux (WSL) 中運行。

***

#### **Q: 是否需要使用 VPN？如何配置 DNS？**

**A:**\
不需要使用 VPN。對於 DNS 配置，系統會自動處理，無需額外配置。

***

希望這些 Q\&A 能幫助您更好地理解 Autonomys（Subspace）專案。如有更多問題，請隨時向我們提問！





[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
