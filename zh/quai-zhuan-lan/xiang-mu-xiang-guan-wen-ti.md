---
cover: ../.gitbook/assets/aa.png
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

#### Q: 本地算力與有效算力有何差異？為什麼存在兩種算力？

**A**:

* **本地算力**: 是設備本身的實際運算能力。
* **有效算力**: 是鏈上實際要求的算力，根據鏈的難度計算。

**差異原因**: 礦池會下發較低難度的工作，部分算力較低的設備能完成這些任務，但未必能滿足鏈上要求的難度，因此兩者數值可能存在差異。

***

#### Q: PoEM 與 PoW 機制有何不同？

**A**:

1. **基本原理**:
   * **PoW**: 工作量證明機制，礦工需完成複雜計算，生成符合難度要求的哈希值來驗證區塊。
   * **PoEM**: 在 PoW 基礎上加入“熵權重”，節點更傾向選擇熵較低的區塊以快速達成共識。
2. **驗證方式**:
   * **PoW**: 節點從多個符合難度的區塊中選擇，可能導致分叉。
   * **PoEM**: 節點根據熵值判斷，優先選擇熵最低的區塊，分叉機率更低。
3. **分叉與一致性**:
   * **PoW**: 分叉後需要額外時間選擇主鏈，最終一致性延遲較高。
   * **PoEM**: 因熵值統一判斷快速達成共識，網絡穩定性更高。
4. **速度與效率**:
   * **PoW**: 區塊確認依賴算力，需等待一致性達成，存在延遲。
   * **PoEM**: 熵權重機制減少確認時間，提高效率並即時解決分叉問題。

**總結**: PoEM 優化了 PoW 的流程，提升了速度與穩定性，減少分叉與延遲。

***

#### Q: QUAI 與 QI 收益策略會隨階段改變，為什麼？

**A**:

1. **收益特性**:
   * **QI**: 與挖礦難度呈線性增長，難度高時收益增加更快。
   * **QUAI**: 與挖礦難度呈對數遞減，難度低時相對收益更高。
2. **收益策略**:
   * **高難度階段**: 優先挖 QI 並將 QUAI 轉換為 QI，以獲取更高收益。
   * **低難度階段**: 優先挖 QUAI 並將 QI 轉換為 QUAI，以提高 QUAI 收益。

***

#### Q: Region 1 向 Region 2 轉賬是否會更快？

**A**: 轉賬速度一致，約 10 秒生成一個區塊即可完成。

***

#### Q: Quai 鏈上有哪些推薦的區塊鏈瀏覽器和錢包工具？

**A**:

* **瀏覽器**: [Quai Explorer](https://cyprus1.colosseum.quaiscan.io/)
* **錢包**:
  * [Pelagus Wallet](https://pelaguswallet.io/)
  * [Koala Wallet](https://koalawallet.io/)



[<mark style="color:blue;">**返回Oula**</mark>](https://oula.network/zh/login)
