---
title: insecure-link
description: Docs のビルドの問題 insecure-link に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 10/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: c22404e624ae85369d7b0b95f44e37d51f847368
ms.sourcegitcommit: ab31cbb17c64a06cab4ffb37b157fd812417a499
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587676"
---
# <a name="insecure-link"></a>insecure-link

> [!IMPORTANT]
> このルールは最初 "提案" として有効になりました。これは、コンテンツ チームがその影響を測定し、各リポジトリをクリーンアップする計画を立てるための時間を与えるためです。 **2019 年 12 月 20 日に "警告" に昇格します**。

## <a name="suggestion"></a>提案

`Link '{URL}' is insecure. Links to Microsoft sites must use 'https' instead of 'http'.`

このメッセージは、`http` の明示的な Markdown リンクを使用したこと、または `www.microsoft.com` などの生の URL を使用したことを意味します。 生の URL は Docs に公開されるときに安全でないリンクに変換されるので、使用しないでください。

## <a name="resolution"></a>解決方法

Microsoft サイトに対するすべての URL を、`http` ではなく `https` を使用するように変更します。

リンクが生の URL の場合は、`https` で始まる明示的な Markdown リンクに変更します。

> [!TIP]
> VS Code 用 Docs Markdown 拡張機能には、Microsoft リンク用のクリーンアップ スクリプトが含まれています。 そのスクリプトでリポジトリ内の Microsoft サイトへのすべてのリンクがチェックされ、`http` ではなく `https` で始まっていること、および`en-us` のようなロケール コードが含まれないことが確認されます。 スクリプトを実行するには、次のようにします。
>
> 1. VS Code 用の [Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) 拡張機能をインストールします。
> 1. Alt + M キーを押して、[Markdown] メニューを開きます。
> 1. **[Cleanup]\(クリーンアップ\)** を選択し、 **[Microsoft links]\(Microsoft リンク\)** を選択します。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
