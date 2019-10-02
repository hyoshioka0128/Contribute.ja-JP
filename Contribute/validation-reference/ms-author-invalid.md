---
title: ms-author-invalid
description: Docs のビルドの問題 ms-author-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 9/27/2019
ms.prod: non-product-specific
ms.openlocfilehash: b3100b4a304356aee3c50f805628890b8c738fe1
ms.sourcegitcommit: d2f5b68b6a6d1ac902dba5063482ff5955a5b1f7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71481693"
---
# <a name="ms-author-invalid"></a>ms-author-invalid

## <a name="warning"></a>警告

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not an allowed distribution list.`

## <a name="resolution"></a>解決方法

`ms.author` の値が現在の作成者の有効な Microsoft のエイリアスであるかどうかを確認します。 指定された作成者は、短期間のベンダーではなく、常勤従業員またはチームの配布リスト (DL) であることをお勧めします。 エイリアスが DL である場合は、`ms.author` 許可リストに含まれている必要もあります。

`ms.author` DL に有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
