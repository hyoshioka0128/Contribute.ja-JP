---
title: insecure-link
description: Docs のビルドの問題 insecure-link に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 10/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: 4735d47cdf2029d2c613c9b333a393c7d978c58e
ms.sourcegitcommit: 423d9b8145a11426c91f45510b2d77319838eb27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74528842"
---
# <a name="insecure-link"></a>insecure-link

> [!IMPORTANT]
> このルールは最初 "提案" として有効になりました。これは、コンテンツ チームがその影響を測定し、各リポジトリをクリーンアップする計画を立てるための時間を与えるためです。 **2019 年 12 月 20 日に "警告" に昇格します**。

## <a name="suggestion"></a>提案

`Link '{URL}' is insecure. Links to Microsoft sites must use 'https' instead of 'http'.`

このメッセージは、`http` の明示的な Markdown リンクを使用したこと、または `www.microsoft.com` などの生の URL を使用したことを意味します。 生の URL は Docs に公開されるときに安全でないリンクに変換されるので、使用しないでください。

## <a name="resolution"></a>解決方法

Microsoft サイトに対するすべての URL を、`http` ではなく `https` を使用するように変更します。

リンクが生の URL の場合は、`https` で始まる明示的な Markdown リンクに変更します。たとえば、

```md
`[www.microsoft.com](https://www.microsoft.com)`.
```

> [!TIP]
> VS Code 用 Docs Markdown 拡張機能には、Microsoft リンク用のクリーンアップ スクリプトが含まれています。 そのスクリプトでリポジトリ内の Microsoft サイトへのすべてのリンクがチェックされ、`http` ではなく `https` で始まっていること、および`en-us` のようなロケール コードが含まれないことが確認されます。 スクリプトを実行するには、次のようにします。
>
> 1. VS Code 用の [Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) 拡張機能をインストールします。
> 1. Alt + M キーを押して、[Markdown] メニューを開きます。
> 1. **[Cleanup]\(クリーンアップ\)** を選択し、 **[Microsoft links]\(Microsoft リンク\)** を選択します。

場合によっては、クリック可能なリンクを意図していない Web アドレス (完全修飾ドメイン名など) をドキュメント化する必要があります。 次のように、インライン コードとしてスタイルを設定する必要があります。

```md
`www.microsoft.com:90`
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
