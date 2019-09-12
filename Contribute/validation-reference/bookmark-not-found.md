---
title: internal-bookmark-not-found
description: Docs のビルドの問題 internal-bookmark-not-found に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 9/10/2019
ms.prod: non-product-specific
ms.openlocfilehash: 53b98f8da199e3495cc00b2388d983191268eee6
ms.sourcegitcommit: 89147521f0aa3b39e7ddf390136b09a43d95c416
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856222"
---
# <a name="bookmark-not-found"></a>bookmark-not-found

## <a name="warning"></a>警告

`Cannot find bookmark '{bookmark-id}' in '{parent-file}'.`

現在のファイルまたは別のファイル内の存在しない見出しにリンクしようとしています。

## <a name="resolution"></a>解決方法

[!INCLUDE [docs-authoring-pack](includes/docs-authoring-pack.md)]

リンクする先の見出しを確認し、リンクを更新します。

現在の記事にあるセクションにリンクするには、ハッシュ記号を使用し、その後に見出し語を続けます。 見出しから句読点を削除し、スペースをダッシュに置き換えます。 例を次に示します。

```markdown
[Managed Disks](#managed-disks)
```

別のファイル内の見出しにリンクするには、そのファイルへの相対リンクを使い、その後にハッシュ記号と見出しの単語を続けます。 見出しから句読点を削除し、スペースをダッシュに置き換えます。 例を次に示します。

```markdown
See [the Resolution section in h1-empty](h1-empty.md#resolution).
```

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
