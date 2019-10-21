---
title: h1-in-moniker
description: Docs のビルドの問題 h1-in-moniker に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 10/09/2019
ms.prod: non-product-specific
ms.openlocfilehash: 3730385cfaf86c3a2a6165f1958d644e71ad7b56
ms.sourcegitcommit: 57eb071bdc55ef71fa3f8ac979326c3f8fbe9c45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72246362"
---
# <a name="h1-in-moniker"></a>h1-in-moniker

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>提案

`H1s are not allowed in moniker sections. Each article should have one and only one H1.`

H1 はマークダウン ファイル内の最初の見出しを参照します。 docs.microsoft.com に公開すると、H1 はページの上部に大きなフォントで表示されます。 H1 を作成するには、行を 1 つのハッシュ (#) とスペースで開始して、その後に見出しのテキストを続けます。 各ファイルで使用できる H1 は 1 個のみです。 モニカー セクションでは H1 は許可されていません。これは、モニカー内の H1 が、バージョン管理の構成方法によっては、H1 の重複または欠落の原因になりやすいためです。

また、`=======` のように、モニカー セクションに等号の行が含まれ、二重下線ができる場合にも、このメッセージが表示されることがあります。 これは、H1 の代替 Markdown 構文です。 マージ競合でもよく見られます。

```markdown
<<<<<<< HEAD
...
=======
...
>>>>>>> 1d82c7efe18f86136247fb366df5030843199c19
```

## <a name="resolution"></a>解決方法

この問題を解決するには、すべてのモニカー セクションから H1 を削除し、記事の先頭にある H1 がすべてのモニカー セクションに適していることを確認します。 見出しレベルをスキップすること (H1 の後に H3 を続けるなど) は許可されていないので注意してください。

モニカー セクション内の H1 が実際には二重下線 (`=======`) である場合は、それを削除するか、必要に応じて `##` などのハッシュタグの見出しで置き換えます。 二重下線がマージ競合の一部である場合は、マージ競合の開始マーカーと終了マーカー、および古いテキストも必ず削除してください。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
