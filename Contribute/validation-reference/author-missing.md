---
title: author-missing
description: Docs のビルドの問題 author-missing に関する説明と解決方法。
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: c10bf7936968f876d983c77e64c2a8cb809baae2
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236338"
---
# <a name="author-missing"></a>author-missing

## <a name="warning"></a>警告

`Missing attribute: author. Add the current author's GitHub ID.`

`author` 属性は、GitHub ID によって記事の作成者を識別します。 

## <a name="resolution"></a>解決方法

現在の作成者の GitHub ID を YML ヘッダーに追加します。

```yml
---
author: meganbradley
ms.author: mbradley
---
```

所有権が変更されている場合、これは元の作成者ではなく、記事の*現在*の所有者であるはずです。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
