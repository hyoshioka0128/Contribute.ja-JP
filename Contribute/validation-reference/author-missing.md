---
title: author-missing
description: Docs のビルドの問題 author-missing に関する説明と解決方法。
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 12/12/2018
ms.prod: non-product-specific
ms.openlocfilehash: 33d704d64f4a3a1d96792bb01b403aefb3143eb8
ms.sourcegitcommit: 1311ccbbf38312bfe6947082870bc9e90d38c986
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791498"
---
# <a name="author-missing"></a><span data-ttu-id="6df10-103">author-missing</span><span class="sxs-lookup"><span data-stu-id="6df10-103">author-missing</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="6df10-104">提案</span><span class="sxs-lookup"><span data-stu-id="6df10-104">Suggestion</span></span>

`Missing attribute: author. Add the current author's GitHub ID.`

<span data-ttu-id="6df10-105">`author` 属性は、GitHub ID によって記事の作成者を識別します。</span><span class="sxs-lookup"><span data-stu-id="6df10-105">The `author` attribute identifies the author of the article by GitHub ID.</span></span> 

## <a name="resolution"></a><span data-ttu-id="6df10-106">解決方法</span><span class="sxs-lookup"><span data-stu-id="6df10-106">Resolution</span></span>

<span data-ttu-id="6df10-107">現在の作成者の GitHub ID を YML ヘッダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="6df10-107">Add the current author's GitHub ID to the YML header:</span></span>

```yml
---
author: meganbradley
ms.author: mbradley
---
```

<span data-ttu-id="6df10-108">所有権が変更されている場合、これは元の作成者ではなく、記事の*現在*の所有者であるはずです。</span><span class="sxs-lookup"><span data-stu-id="6df10-108">Note that this should be the *current* owner of the article, not the original author if ownership has changed.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
