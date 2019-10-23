---
title: ms-date-invalid
description: Docs のビルドの問題 ms-date-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 09/10/2019
ms.prod: non-product-specific
ms.openlocfilehash: a54dc495593315a0382ea99e46a86145fbfa8577
ms.sourcegitcommit: 836d4d6127fabb5569ffc0809db5fb25e46038b5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72590892"
---
# <a name="ms-date-invalid"></a>ms-date-invalid

## <a name="warning"></a>警告

`Invalid value for ms.date: '{value}'. Must be a date in format MM/DD/YYYY, no more than 30 days from today.`

## <a name="resolution"></a>解決方法

記事が最新で、壊れたコンテンツがないことを確認した後、有効な日付を MM/DD/YYYY の形式で追加します。

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
