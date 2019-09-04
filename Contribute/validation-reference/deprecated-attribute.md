---
title: deprecated-attribute
description: Docs のビルドの問題 deprecated-attribute に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 15d285159b361b7fb9dbc1774e6c4b2f5f5758ed
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236190"
---
# <a name="deprecated-attribute"></a>deprecated-attribute

## <a name="warning"></a>警告

`Deprecated attribute: ms.component. Use ms.subservice instead.`

`ms.service` を使ってクラウド サービスを指定します。 `ms.service` に関する詳細情報を指定する場合は、必要に応じて `ms.subservice` を指定できます。 `ms.component` は使用しないでください。このコンテンツでは非推奨です。

## <a name="resolution"></a>解決方法

`ms.service` の値がご自分の記事に対して適切であることを確認します。 次に、有効な `ms.subservice` の値を選びます。

有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
