---
title: h1-missing
description: Docs のビルドの問題 h1-missing に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 11/25/2019
ms.prod: non-product-specific
ms.openlocfilehash: 1ff29a06b5a8d53d0152329807acc416463f4fe2
ms.sourcegitcommit: 423d9b8145a11426c91f45510b2d77319838eb27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74528898"
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
> このルールはインクルード ファイルには適用されません。 インクルード ファイルに対して H1 の結果が表示された場合、大抵はインクルード ファイルを `includes` フォルダーに移動する必要があります。 `includes` フォルダーは、ファイル パス内の任意のレベルに置くことができます。 パスに基づいて Docs のビルドではファイルがインクルード ファイルとして認識され、H1 の検証は実行されません。
>
> 親ファイル内に H1 が見つからないケースは、多くの場合、インクルード ファイルの誤用、すなわち H1 を親ファイルではなくインクルード ファイルに含めていることが原因です。 これは許可されません。なぜなら、インクルード ファイル内で H1 を使用することは、親ファイルに重複する H1 が含まれるか、またはインクルード ファイルが 1 回しか使用されないことを意味するからです。 H1 はコンテンツ セット内で一意である必要があり、インクルード ファイルは複数のファイル間でコンテンツを共有するためにのみ使用する必要があります。 H1 がインクルード ファイルに含まれているために `h1-missing` の結果が表示された場合、解決策は、その H1 (と、そのインクルード ファイルが 1 回しか使用されない場合はインクルードされるすべてのコンテンツ) を親ファイルに移動することです。 Docs のインクルード ファイルについて詳しくは、Microsoft の内部記事「[再利用可能なコンテンツを記事にインクルードする](https://review.docs.microsoft.com/en-us/help/contribute/includes-best-practices?branch=master)」をご覧ください。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
