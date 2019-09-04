---
title: ms-prod-and-technology-invalid
description: Docs のビルドの問題 ms-prod-and-technology-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: 25a2b6a5bcb63388c119863ea82fb932dda4eec8
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236345"
---
# <a name="ms-prod-and-technology-invalid"></a>ms-prod-and-technology-invalid

## <a name="warning"></a>警告

`Invalid value for ms.prod: '{value}'.`

`Invalid value for ms.technology: '{value}' is not valid with ms.prod value '{value}'.`

オンプレミスの製品を指定する場合は `ms.prod` を使います。 `ms.prod` に関する詳細情報を指定する場合は、必要に応じて `ms.technology` を指定できます。 `ms.prod` と `ms.technology` に対する値は有効なペアである必要があります。 `ms.prod` の値が無効であるか、`ms.technology` の値が `ms.prod` と有効なペアになっていないかのどちらかです。

## <a name="resolution"></a>解決方法

`ms.prod` の値がご自分の記事に対して適切であることを確認します。 次に、有効な `ms.technology` の値を選びます。

有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。 新しい値を要求するには、[この手順](https://review.docs.microsoft.com/help/contribute/metadata-changes?branch=master)に従います。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
