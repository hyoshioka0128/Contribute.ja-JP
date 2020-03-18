---
title: リダイレクトの並べ替え - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack を使用してリダイレクトを並べ替える方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: 4924c631c8720743c283083e53b3a1e9af86b00a
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336683"
---
# <a name="sort-redirects"></a>リダイレクトの並べ替え

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

docs.microsoft.com docset が進化するに従って、一部の Markdown ファイルは最終的に削除されます。 Markdown ファイルを削除する場合、削除される記事の参照がリダイレクトを通じて適切に解決されるように、リダイレクトを提供する必要があります。 リダイレクトは、" *.openpublishing.redirection.json*" ファイルで指定されます。

1. コマンド パレットを開いて、<kbd>F1</kbd> キー (または macOS の場合、<kbd>⇧⌘P</kbd>) を押します。
1. 次のように入力します: **Docs: マスター リダイレクト ファイルの並べ替え**
1. コマンドを選択して、これを実行します。
1. " *.openpublishing.redirection.json*" ファイルに対する変更を監視します。

## <a name="considerations"></a>考慮事項

" *.openpublishing.redirection.json*" ファイルの当初の設計方法には、"デイジー チェーン" という概念が存在します。 時間の経過に伴って、リダイレクトとして追加されたファイルは最終的に古くなります。 これは、ファイル A が削除され、ファイル B へのリダイレクトが必要になり、その後、ファイル B が削除され、ファイル C へのリダイレクトが必要になった場合に発生します。両方のエントリが C を指し、A が C にリダイレクトし、B は変わらないのが理想的です。 これにより、パフォーマンスがわずかに向上するため、この機能に積極的に取り組んでいます。

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![リダイレクトの並べ替えのデモ](media/sort-redirect.gif)](media/sort-redirect.gif#lightbox)
