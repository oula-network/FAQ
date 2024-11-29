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

# 👨‍🔧 Piece Conversion Tool

### Autonomys Piece Conversion Tool

The Autonomys Piece Conversion Tool allows you to convert data synchronized by `autonomys-node` into `piece` cache data. Please follow the steps below to export `piece` cache data:

1.  Use the following command:

    ```bash
    NODE_URL="http://192.168.1.1:9944" ./autonomys-export-piece
    ```
2. After executing the command, the generated `piece` data will be automatically saved to the `full-cache-tmp` directory on your local machine.
3. Simply set the `path` parameter of the `autonomys-full-piece` component to this directory.

{% hint style="warning" %}
**Note**: The startup command for `autonomys-node` specified in `NODE_URL` must include the **`--sync=full --blocks-pruning=archive`** parameter.
{% endhint %}



