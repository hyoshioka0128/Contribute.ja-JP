---
title: ms-author-invalid
description: Docs のビルドの問題 ms-author-invalid に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/28/2019
ms.prod: non-product-specific
ms.openlocfilehash: 1ae01c34ea60cec30698d7e11264d05c3f398d1c
ms.sourcegitcommit: 1311ccbbf38312bfe6947082870bc9e90d38c986
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791550"
---
# <a name="ms-author-invalid"></a><span data-ttu-id="8e1a6-103">ms-author-invalid</span><span class="sxs-lookup"><span data-stu-id="8e1a6-103">ms-author-invalid</span></span>

[!INCLUDE [suggestion-note](includes/suggestion-note.md)]

## <a name="suggestion"></a><span data-ttu-id="8e1a6-104">提案</span><span class="sxs-lookup"><span data-stu-id="8e1a6-104">Suggestion</span></span>

`Invalid value for ms.author: '{value}' is not a valid Microsoft alias, or is not an allowed distribution list.`

## <a name="resolution"></a><span data-ttu-id="8e1a6-105">解決方法</span><span class="sxs-lookup"><span data-stu-id="8e1a6-105">Resolution</span></span>

<span data-ttu-id="8e1a6-106">`ms.author` の値が現在の作成者の有効な Microsoft のエイリアスであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e1a6-106">Verify that the `ms.author` value is the current author's valid Microsoft alias.</span></span> <span data-ttu-id="8e1a6-107">エイリアスが配布リストである場合は、許可リストに含まれている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8e1a6-107">If the alias is a distribution list, it must also be on the allow list.</span></span>

<span data-ttu-id="8e1a6-108">DL に有効な値は、[こちらの Microsoft 内部サイト](https://docsmetadatatool.azurewebsites.net/allowlists)にあります。</span><span class="sxs-lookup"><span data-stu-id="8e1a6-108">Valid values for DLs can be found on [this Microsoft-internal site](https://docsmetadatatool.azurewebsites.net/allowlists).</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
