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

# 👨‍🔧 Autonomys Piece 轉換工具

{% embed url="https://oula.network/zh/" %}

### Autonomys Piece 轉換工具

可以將 `autonomys-node` 同步後的數據轉換為 `piece cache`數據，請按照以下步驟導出 `piece cache` 數據：

1.  使用命令：

    ```bash
    NODE_URL="http://192.168.1.1:9944" ./autonomys-export-piece
    ```
2. 運行指令後，生成的 `piece` 數據會自動儲存至本機的 `full-cache-tmp` 資料夾。
3. 在使用 `autonomys-full-piece` 組件時，將 `path` 參數指定為該目錄即可。

{% hint style="warning" %}
`NODE_URL` 中指定的 `autonomys-node` 啟動指令必須包含 **`--sync=full --blocks-pruning=archive`** 參數。
{% endhint %}





[**返回Oula**](https://oula.network/zh/login)
