---
cover: ../.gitbook/assets/Quai.png
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

# 🔍 项目相關問題

{% embed url="https://oula.network/zh/" %}

#### Q: PoEM和PoW有什麼區別？

A:

1. **基本原理**：
   * **PoW（工作量證明）**：通過讓礦工完成複雜的計算任務來生成符合特定難度要求的哈希值，以此驗證區塊的有效性。礦工競爭生成合格的哈希值，最先完成的礦工獲得獎勵。
   * **PoEM（熵權重證明）**：在PoW基礎上引入“熵權重”概念，除滿足難度要求外，還會對每個區塊的熵（隨機性）進行計算，節點會優先選擇熵最低的區塊進行驗證和添加。
2. **驗證方式**：
   * **PoW**：礦工可以從達到難度門檻的所有區塊中自由選擇，這可能導致不同節點在不同時間選擇不同的區塊，進而造成分叉。
   * **PoEM**：通過熵權重計算，節點會一致選擇熵最低的區塊，減少分叉並更快達成共識。
3. **分叉與一致性**：
   * **PoW**：節點對區塊確認的延遲容易導致分叉，網絡需額外時間選擇主鏈以達成一致性。
   * **PoEM**：由於節點對區塊權重有一致的判斷，能迅速選擇相同的“最佳”區塊，避免分叉，提高穩定性。
4. **速度與效率**：
   * **PoW**：每個區塊的添加依賴於礦工的計算能力，並需等待網絡一致性確認，導致延遲。
   * **PoEM**：通過熵權重機制，節點可立即確定下一個區塊，縮短共識時間，提高效率。

**總結**：PoEM通過引入熵權重優化了PoW的共識流程，使網絡更快、更穩定地達成共識，減少分叉並降低確認延遲。

***

#### Q: QUAI和QI收益的公式是什麼？為什麼在不同階段策略會有所不同？

A:

1. **QUAI與QI的發行機制**：
   * **QI**：發行量與挖礦難度呈線性關係，難度增加時，QI的發行量按固定比例增長。高難度時，QI的收益增幅較大。
   * **QUAI**：發行量與挖礦難度呈對數遞減關係，難度升高時，QUAI的發行量增幅變小甚至減少。低難度時，QUAI的收益相對更有優勢。
2. **收益最大化策略**：
   * **高難度階段（算力高）**：選擇挖QI收益更高，並將已有的QUAI兌換為QI以獲取更多收益。
   * **低難度階段（算力低）**：選擇挖QUAI收益更高，並將已有的QI兌換為QUAI以提高整體收益。

***

#### Q: Region 1向Region 2轉帳的速度如何？

A: 兩個區域之間的轉帳速度是一致的，**每10秒生成一個區塊**。

***

#### Q: 如何使用Quai區塊瀏覽器查詢？

A: 您可以通過以下鏈接訪問Quai區塊瀏覽器進行查詢：[**Quai區塊瀏覽器**](https://quaiscan.io)**。**

***

#### Q: 推薦的錢包有哪些？

A: 以下是推薦的Quai錢包：

* [**Pelagus Wallet**](https://pelaguswallet.io/)
* [**Koala Wallet**](https://koalawallet.io/)





[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
