---
title: ms-service-and-subservice-invalid
description: Docs のビルドの問題 ms-service-and-subservice-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 1/15/2019
ms.prod: non-product-specific
ms.openlocfilehash: a6059d592212b271780344a086ee68c7133e15cd
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236513"
---
# <a name="ms-service-and-subservice-invalid"></a>ms-service-and-subservice-invalid

## <a name="warning"></a>警告

`Invalid value for ms.service: '{value}'.`

`Invalid value for ms.subservice: '{value}' is not valid with ms.service value '{value}'.`

`ms.service` を使ってクラウド サービスを指定します。 `ms.service` に関する詳細情報を指定する場合は、必要に応じて `ms.subservice` を指定できます。 `ms.service` と `ms.subservice` に対する値は有効なペアである必要があります。 `ms.service` の値が無効であるか、`ms.subservice` の値が `ms.service` と有効なペアになっていないかのどちらかです。

## <a name="resolution"></a>解決方法

`ms.service` の値がご自分の記事に対して適切であることを確認します。 次に、有効な `ms.subservice` の値を選びます。

有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。 新しい値を要求するには、[この手順](https://review.docs.microsoft.com/help/contribute/metadata-changes?branch=master)に従います。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
