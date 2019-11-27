---
title: h1-empty
description: Docs のビルドの問題 h1-empty に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 11/25/2019
ms.prod: non-product-specific
ms.openlocfilehash: d0b3ab2206d66ff68a967d7868353b5b399da80a
ms.sourcegitcommit: 423d9b8145a11426c91f45510b2d77319838eb27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74528807"
---
# <a name="h1-empty"></a>h1-empty

## <a name="warning"></a>警告

`H1 is required. Add content to your top-level heading.`

H1 はマークダウン ファイル内の最初の見出しを参照します。 docs.microsoft.com に公開すると、H1 はページの上部に大きなフォントで表示されます。 H1 を作成するには、行を 1 つのハッシュ (#) とスペースで開始して、その後に見出しのテキストを続けます。

## <a name="resolution"></a>解決方法

この問題を解決するには、ご利用の H1 に、ハッシュだけでなくコンテンツも必ず含めます。

悪い:

```markdown
---
author: meganbradley
ms.author: mbradley
---
#
This is not an H1
```

良い:

```markdown
---
author: meganbradley
ms.author: mbradley
---
# This is an H1
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
