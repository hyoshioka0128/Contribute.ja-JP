---
title: h1-not-first
description: Docs のビルドの問題 h1-not-first に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 09/10/2019
ms.prod: non-product-specific
ms.openlocfilehash: c5e2eeeb5c464cd2923e23110cdab9a83324e53e
ms.sourcegitcommit: 89ec9772d9cc8281c633833c6fa51f629e9cd566
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895464"
---
# <a name="h1-not-first"></a>h1-not-first

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a>提案

`Markdown content is not allowed before H1.`

マークダウン ファイルの H1 の前には、YAML メタデータ ヘッダーのみを使用できます。 たとえば、記事の上部にノートや画像を追加する場合は、H1 の後に置く必要があります。 次のものは使用できません。

```markdown
---
# This is the YAML metadata header
author: meganbradley
---
> [!NOTE]
> You can't do this.

# This is the H1
```

代わりに、次を実行します。

```markdown
---
# This is the YAML metadata header
author: meganbradley
---
# This is the H1

> [!NOTE]
> This is OK.
```

この問題のもう 1 つの一般的な原因は、YAML ヘッダーより前の[バイト オーダー マーク (BOM)](http://www.websina.com/bugzero/kb/unicode-bom.html) です。 これらは、コンテンツをリポジトリにコミットするときに、エンコードの問題によって発生することがあります。 このような場合は、GitHub でのレンダリングに問題があるため、削除する必要があります。

## <a name="resolution"></a>解決方法

H1 の前から、YAML メタデータ ヘッダー以外のコンテンツをすべて削除します。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
