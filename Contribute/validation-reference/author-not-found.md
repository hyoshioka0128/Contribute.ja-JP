---
title: author-not-found
description: Docs のビルドの問題 author-not-found に関する説明と解決方法。
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/26/2019
ms.prod: non-product-specific
ms.openlocfilehash: af4145b4f6be07f07a22842e6ded279e8390b054
ms.sourcegitcommit: 1311ccbbf38312bfe6947082870bc9e90d38c986
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791586"
---
# <a name="author-not-found"></a><span data-ttu-id="f59da-103">author-not-found</span><span class="sxs-lookup"><span data-stu-id="f59da-103">author-not-found</span></span>

## <a name="warning"></a><span data-ttu-id="f59da-104">警告</span><span class="sxs-lookup"><span data-stu-id="f59da-104">Warning</span></span>

`Invalid value for author: '{value}' is not a valid GitHub ID.`

## <a name="resolution"></a><span data-ttu-id="f59da-105">解決方法</span><span class="sxs-lookup"><span data-stu-id="f59da-105">Resolution</span></span>

<span data-ttu-id="f59da-106">現在の作成者の GitHub ID を `author` 値として追加します。</span><span class="sxs-lookup"><span data-stu-id="f59da-106">Add the current author's GitHub ID as the `author` value.</span></span>

<span data-ttu-id="f59da-107">所有権が変更されている場合、これは元の作成者ではなく、記事の*現在*の所有者であるはずです。</span><span class="sxs-lookup"><span data-stu-id="f59da-107">Note that this should be the *current* owner of the article, not the original author if ownership has changed.</span></span>

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
