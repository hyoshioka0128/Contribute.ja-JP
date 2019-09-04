---
title: title-missing
description: Docs のビルドの問題 title-missing に関する説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 2/6/2019
ms.prod: non-product-specific
ms.openlocfilehash: cfe942be4285bb22f5fa08fa882077ea790fd2c4
ms.sourcegitcommit: dd751d0cb5b11f81a64ef62f3c83fd17cc5f0541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236557"
---
# <a name="title-missing"></a>title-missing

## <a name="warning"></a>警告

`Missing attribute: title. Add a title string (19 - 59 characters) to show in search engine results.`

## <a name="resolution"></a>解決方法

検索結果に表示されるタイトルの文字列を追加します。 一般的に、タイトルは 19 から 59 文字にする必要があり、記事の H1 とは別にする必要があり、関連するブランドの文字を含める必要があります。 タイトルに " | Microsoft Docs" は含めないでください。これは Docs によって自動的に追加され、明示的に追加した場合は無視されます。 " - Azure" などの他のブランドをコンテンツ セット内のすべてのタイトルに追加する場合は、`titleSuffix` メタデータ値をグローバルに設定するか、フォルダーに対して設定します。

ご自分のタイトルが Google でどのように表示されるかは、[https://moz.com/learn/seo/title-tag](https://moz.com/learn/seo/title-tag) でプレビューできます。

Microsoft 社員の場合、優れたタイトルと検索エンジンの最適化 (SEO) について詳しくは、内部の共同作成者ガイドにある [SEO の基礎](https://review.docs.microsoft.com/en-us/help/contribute/contribute-how-to-write-seo-basics?branch=master)に関するページをご覧ください。

[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
