---
title: insecure-link
description: Docs のビルドの問題 insecure-link に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 10/1/2019
ms.prod: non-product-specific
ms.openlocfilehash: b97d4c4a0f61e5f3448331a56fe4bde442ff1cca
ms.sourcegitcommit: 0cb0177c209abab1a72af4f411ef527fa5cf10f9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379525"
---
# <a name="insecure-link"></a>insecure-link

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

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
