---
title: h1-missing
description: Docs のビルドの問題 h1-missing に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 677127d09349445bb80778dfb501d7d4294ea46b
ms.sourcegitcommit: 89147521f0aa3b39e7ddf390136b09a43d95c416
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848483"
---
# <a name="h1-missing"></a>h1-missing

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>提案

`H1 is required. Use a single hash (#) followed by a space to create your top-level heading.`

H1 はマークダウン ファイル内の最初の見出しを参照します。 docs.microsoft.com に公開すると、H1 はページの上部に大きなフォントで表示されます。 H1 を作成するには、行を 1 つのハッシュ (#) とスペースで開始して、その後に見出しのテキストを続けます。

## <a name="resolution"></a>解決方法

この問題を解決するには、ご利用のファイル内の YML メタデータ ブロックの後に、H1 を最初のコンテンツとして追加します。

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

> [!NOTE]
> このルールはインクルード ファイルには適用されません。 インクルード ファイルに対して H1 の警告が表示された場合、大抵はインクルード ファイルを `includes` フォルダーに移動する必要があります。 `includes` フォルダーは、ファイル パス内の任意のレベルに置くことができます。 パスに基づいて Docs のビルドではファイルがインクルード ファイルとして認識され、H1 の検証は実行されません。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]