---
title: multiple-h1
description: Docs のビルドの問題 multiple-h1 に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: a1006d9d75ebd53751c9ab81aa016d67d6e5df57
ms.sourcegitcommit: 89147521f0aa3b39e7ddf390136b09a43d95c416
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848607"
---
# <a name="multiple-h1"></a>multiple-h1

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>提案

`Multiple H1s are not allowed. You can only have one top-level heading.`

H1 はマークダウン ファイル内の最初の見出しを参照します。 docs.microsoft.com に公開すると、H1 はページの上部に大きなフォントで表示されます。 H1 を作成するには、行を 1 つのハッシュ (#) とスペースで開始して、その後に見出しのテキストを続けます。 各ファイルで使用できる H1 は 1 個のみです。

## <a name="resolution"></a>解決方法

この問題を解決するには、後続の H1 の見出しレベルを H2 (`##`) に変更するか、あるいはファイルを再構成します。 見出しレベルをスキップする (H1 の後に H3 を続ける) ことは許可されていないので注意してください。

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1

Some content...

## This is an H2
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]