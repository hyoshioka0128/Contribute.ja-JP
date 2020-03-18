---
title: 選択範囲の並べ替え - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack から選択範囲の並べ替え機能を使用する方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: b4bd1761dc1bd9326275f011bb1935f6b695404d
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336752"
---
# <a name="sort-selection"></a>選択範囲の並べ替え

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

Markdown (" *\*.md*") ファイルで、選択を行ったときに、2 つの並べ替えコンテキスト メニュー項目を使用できるようになりました。 選択したテキストを右クリックして、コンテキスト メニューを開きます。 次のようなメニュー項目が表示されます。

:::image type="content" source="media/sort-selection-menu.png" alt-text="選択範囲の並べ替えコンテキスト メニュー":::

> [!TIP]
> 並べ替えコンテキスト メニュー項目は、Visual Studio Code テキスト エディターで有効な選択が行われるまで表示されません。

## <a name="sort-selection-ascending-a-to-z"></a>選択範囲を昇順に並べ替え (A から Z)

**[Sort selection ascending (A to Z)]\(選択範囲を昇順に並べ替え (A から Z)\)** オプションを選択すると、選択範囲全体が昇順 (A から Z のアルファベット順) に並べ替えられます。

## <a name="sort-selection-descending-z-to-a"></a>選択範囲を降順に並べ替え (Z から A)

**[Sort selection descending (Z to A)]\(選択範囲を降順に並べ替え (Z から A)\)** オプションを選択すると、選択範囲全体が降順 (Z から A のアルファベット順) に並べ替えられます。

## <a name="considerations"></a>考慮事項

基になる並べ替えメカニズムでは、"*自然言語*" の並べ替えが使用されます。 これにより、並べ替えが標準の並べ替えよりも強力で包括的になります。 次の表について考えてみましょう。

```markdown
| Column1 | Column2                                |
|---------|----------------------------------------|
| 1       | Number 1                               |
| Aa      | The first letter in the alphabet       |
| Ab      | The first letter in the alphabet       |
| C       | The a letter after A in the alphabet   |
| M       | Somewhere in the middle?               |
| 2       | Number 2                               |
| X       | The alphabet letter is towards the end |
| Z       | The last letter in the alphabet        |
| 11      | Number 11                              |
```

自然言語の並べ替えを使用しない場合、`Column1`の順序は、1、11、2 というようになりますが、自然言語の並べ替えでは、11 は 2 より大きいことが認識され、次のような昇順になります。

```markdown
| Column1 | Column2                                |
|---------|----------------------------------------|
| 1       | Number 1                               |
| 2       | Number 2                               |
| 11      | Number 11                              |
| Aa      | The first letter in the alphabet       |
| Ab      | The first letter in the alphabet       |
| C       | The a letter after A in the alphabet   |
| M       | Somewhere in the middle?               |
| X       | The alphabet letter is towards the end |
| Z       | The last letter in the alphabet        |
```

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![選択範囲の並べ替えのデモ](media/sort-selection.gif)](media/sort-selection.gif#lightbox)
