---
title: multiple-values
description: Docs のビルドの問題 multiple-values に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/19/2019
ms.prod: non-product-specific
ms.openlocfilehash: 515a8cd76cbd3d9bd117b1d0d59492f4a77bea4c
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236473"
---
# <a name="multiple-values"></a>multiple-values

## <a name="warning"></a>警告

`Single-valued attribute {attribute} has multiple values. Remove additional values.`

単一の値しか許可されていない属性に対して、複数の値を指定しました。

`Single-valued attribute {attribute} is in multi-valued array format. Change to scalar format.`

複数の値を持つことが許可されていない属性は、単一値 (スカラー) の YML 形式で指定する必要があります。

## <a name="resolution"></a>解決方法

複数値の配列を単一値の属性に対して使った場合、配列内に複数の値、単一の値のどちらが含まれていても、必ずこの提案が発生します。

YML では、`ms.custom` などの複数値の属性に対して、次の配列形式がサポートされています。

```yml
---
# comma-separated bracketed list:
ms.custom: [WIP, generated-via-CI]

# each value on its own line:
ms.custom:
  - WIP
  - generated-via-CI
---
```

これらの形式は、`author` などの単一値の属性に対しては有効ではありません。

複数の値を指定した場合は、指定した値を確認していずれが正しいのか判断します。 次のように、他の値を削除し、同じ行に属性としてブラケットを含まない単一の値を指定します。

```yml
---
author: meganbradley
---
```

単一値の配列がある場合は、それを上のスカラー形式に変更します。

## <a name="attributes-in-scope"></a>スコープ内の属性

次の属性は単一値である必要があります。

- `author`
- `ms.author`
- `ms.date`
- `ms.prod`
- `ms.service`
- `ms.subservice`
- `ms.technology`
- `ms.topic`
- `title`

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
