---
title: ms-date-invalid
description: Docs のビルドの問題 ms-date-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 09/10/2019
ms.prod: non-product-specific
ms.openlocfilehash: 46cd047253fc7fbfdf92b0c5a6d690e041262b02
ms.sourcegitcommit: 89ec9772d9cc8281c633833c6fa51f629e9cd566
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895437"
---
# <a name="ms-date-invalid"></a>ms-date-invalid

## <a name="warning"></a>警告

`Invalid value for ms.date: '{value}'. Must be a date in format MM/DD/YYYY, no more than five days from today.`

## <a name="resolution"></a>解決方法

記事が最新で、壊れたコンテンツがないことを確認した後、有効な日付を MM/DD/YYYY の形式で追加します。

```yml
---
ms.date: 02/19/2019
---
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
