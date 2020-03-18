---
title: Markdown テーブルの再フォーマット - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack から Markdown テーブルのさまざまなフォーマット機能を使用する方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: 07c95f2a0d24a49f59eaffe1bec64ee872530c2f
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336775"
---
# <a name="reformat-markdown-tables"></a>Markdown テーブルの再フォーマット

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

Markdown (" *\*.md*") ファイルで、完全なテーブルを選択したときに、テーブルのフォーマット用に 2 つのコンテキスト メニュー項目を使用できるようになりました。 選択した Markdown テーブルを右クリックしてコンテキスト メニューを開きます。 次のようなメニュー項目が表示されます。

:::image type="content" source="media/reformat-table-menu.png" alt-text="テーブルの再フォーマット コンテキスト メニュー":::

> [!TIP]
> この機能は、複数のテーブルでは**動作せず**、1 つの Markdown テーブルだけを対象とします。 目的の結果を得るには、見出しを含めてテーブル全体を選択する必要があります。

## <a name="consolidate-selected-table"></a>選択したテーブルの統合

**[Consolidate selected table]\(選択したテーブルを統合する\)** オプションを選択すると、テーブルの見出しと内容が折りたたまれ、各値の両側のスペースは 1 文字だけになります。

## <a name="evenly-distribute-selected-table"></a>選択したテーブルの均等配置

**[Evenly distribute selected table]\(選択したテーブルを均等に配置する\)** オプションを選択すると、各列の最も長い値が計算され、それに応じて、他のすべての値が、スペースを使用して均等に配置されます。

## <a name="considerations"></a>考慮事項

この機能は、テーブルのレンダリングに影響を与えるものではなく、テーブルの見やすさを向上するのに役立ちます。したがって、保守も容易になります。 テーブルの再フォーマット機能では、列の配置はそのまま維持されます。

次の表について考えてみましょう。

```markdown
| Column1 | This is a long column name | Column3 |  |
|--:|---------|:--:|:----|
||         |  |         |
|     |  |         |   a value      |
||         |         |         |
|     |         | This is a long value |       but why? |
|     |         |         |         |
|     |                                           |         | Here is something |
|  |         |   |         |
```

"均等に配置" 後:

```markdown
| Column1 | This is a long column name | Column3              |                   |
|--------:|----------------------------|:--------------------:|:------------------|
|         |                            |                      |                   |
|         |                            |                      | a value           |
|         |                            |                      |                   |
|         |                            | This is a long value | but why?          |
|         |                            |                      |                   |
|         |                            |                      | Here is something |
|         |                            |                      |                   |
```

"統合" 後:

```markdown
| Column1 | This is a long column name | Column3 |  |
|-:|--|:-:|:-|
|  |  |  |  |
|  |  |  | a value |
|  |  |  |  |
|  |  | This is a long value | but why? |
|  |  |  |  |
|  |  |  | Here is something |
|  |  |  |  |
```

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![テーブルの再フォーマットのデモ](media/reformat-table.gif)](media/reformat-table.gif#lightbox)
