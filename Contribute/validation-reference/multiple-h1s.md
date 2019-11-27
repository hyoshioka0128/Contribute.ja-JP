---
title: multiple-h1s
description: Docs のビルドの問題 multiple-h1s に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 11/25/2019
ms.prod: non-product-specific
ms.openlocfilehash: e2912066895494e221181f2de2bb117ff9ed1636
ms.sourcegitcommit: 423d9b8145a11426c91f45510b2d77319838eb27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74528936"
---
# <a name="multiple-h1s"></a>multiple-h1s

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>提案

`Multiple H1s are not allowed. You can only have one top-level heading.`

H1 はマークダウン ファイル内の最初の見出しを参照します。 docs.microsoft.com に公開すると、H1 はページの上部に大きなフォントで表示されます。 H1 を作成するには、行を 1 つのハッシュ (#) とスペースで開始して、その後に見出しのテキストを続けます。 各ファイルで使用できる H1 は 1 個のみです。

`=======` のように、記事に等号の行が含まれ、二重下線ができる場合にも、このメッセージが表示されることがあります。 これは、H1 の代替 Markdown 構文です。 マージ競合でもよく見られます。

```markdown
<<<<<<< HEAD
...
=======
...
>>>>>>> 1d82c7efe18f86136247fb366df5030843199c19
```

## <a name="resolution"></a>解決方法

この問題を解決するには、後続の H1 の見出しレベルを H2 (`##`) に変更するか、あるいはファイルを再構成します。 見出しレベルをスキップすること (H1 の後に H3 を続けるなど) は許可されていないので注意してください。

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1

Some content...

## This is an H2
```

追加の H1 が実際には二重下線 (`=======`) である場合は、それを削除するか、必要に応じて `##` などのハッシュタグの見出しで置き換えます。 二重下線がマージ競合の一部である場合は、マージ競合の開始マーカーと終了マーカー、および古いテキストも必ず削除してください。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
