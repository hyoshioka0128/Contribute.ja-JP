---
title: ms-author-missing
description: Docs のビルドの問題 ms-author-missing に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/20/2018
ms.prod: non-product-specific
ms.openlocfilehash: 6b313bd6b168b913d82721607126fcd4e6255009
ms.sourcegitcommit: 57eb071bdc55ef71fa3f8ac979326c3f8fbe9c45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72246249"
---
# <a name="ms-author-missing"></a>ms-author-missing

## <a name="warning"></a>警告

`Missing attribute: ms.author. Add the current author's Microsoft alias.`

## <a name="resolution"></a>解決方法

現在の作成者の `ms.author` の Microsoft のエイリアスを追加します。 所有権が変更されている場合、これは元の作成者ではなく、記事の*現在*の所有者であるはずです。 指定された作成者は、短期間のベンダーではなく、常勤従業員またはチームの配布リスト (DL) であることをお勧めします。 

エイリアスが DL である場合は、`ms.author` 許可リストに含まれている必要もあります。

`ms.author` DL に有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
