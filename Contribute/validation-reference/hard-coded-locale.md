---
title: hard-coded-locale
description: Docs のビルドの問題 hard-coded-locale に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 10/18/2019
ms.prod: non-product-specific
ms.openlocfilehash: 0fbc7634e00202fdfdf607b9504744a6d9846792
ms.sourcegitcommit: 836d4d6127fabb5569ffc0809db5fb25e46038b5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72590862"
---
# <a name="hard-coded-locale"></a>hard-coded-locale

> [!IMPORTANT]
> このルールは最初 "提案" として有効になりました。これは、コンテンツ チームがその影響を測定し、各リポジトリをクリーンアップする計画を立てるための時間を与えるためです。 **2019 年 12 月 20 日に "警告" に昇格します**。

## <a name="suggestion"></a>提案

`Link '{URL}' contains locale code '{code}'. For localizability, remove '{code}' from links to Microsoft sites.`

特定の Microsoft サイトへのリンクにロケールのコード (`en-us` など) を含めるべきではありません。 英語のコンテンツ内のリンクにロケールのコードを含めた場合、それはローカライズされたリンクにも含まれることになり、ローカライズのエクスペリエンスが損なわれます。 たとえば、ドイツ語にローカライズされたコンテンツ内のリンクが `en-us` を含んでいた場合、ドイツ語を使用するお客様が、ドイツ語の記事があるにもかかわらず英語の記事にリンクされることになります。

以下のサイトはこの検証の対象に含まれます。

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com

## <a name="resolution"></a>解決方法

Microsoft のサイトへのリンクからロケールのコードを削除してください。 例を次に示します。

変更前:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

変更後:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

> [!TIP]
> VS Code 用 Docs Markdown 拡張機能には、Microsoft リンク用のクリーンアップ スクリプトが含まれています。 そのスクリプトでリポジトリ内の Microsoft サイトへのすべてのリンクがチェックされ、`http` ではなく `https` で始まっていること、および`en-us` のようなロケール コードが含まれないことが確認されます。 スクリプトを実行するには、次のようにします。
>
> 1. VS Code 用の [Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) 拡張機能をインストールします。
> 1. Alt + M キーを押して、[Markdown] メニューを開きます。
> 1. **[Cleanup]\(クリーンアップ\)** を選択し、 **[Microsoft links]\(Microsoft リンク\)** を選択します。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
