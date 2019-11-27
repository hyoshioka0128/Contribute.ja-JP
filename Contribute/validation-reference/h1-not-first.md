---
title: h1-not-first
description: Docs のビルドの問題 h1-not-first に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 11/25/2019
ms.prod: non-product-specific
ms.openlocfilehash: 09b91577f4c87125a92c0c116bc07bc7206c6833
ms.sourcegitcommit: 423d9b8145a11426c91f45510b2d77319838eb27
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74528912"
---
# <a name="h1-not-first"></a>h1-not-first

## <a name="warning"></a>警告

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
