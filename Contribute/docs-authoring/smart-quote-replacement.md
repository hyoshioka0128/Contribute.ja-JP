---
title: スマート クォートの自動置換 - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack を使用してスマート クォートを自動的に置き換える方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: 048f244324d7dde540c78e6631ccb5abbed3e431
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336706"
---
# <a name="smart-quote-replacement"></a>スマート クォートの置換

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

コンテンツ開発者は、最新のテクノロジおよびインテリジェンスの最も高度な機能のいくつかを作成する責任がありますが、現在、Microsoft のツールでは、Markdown で "ダム引用符" を使用することが推奨されます。 反意語はもちろん "スマートクオート" です。 スマート クォートは、理想的なタイポグラフィではよく見られますが、Markdown やレンダリングされた HTML には適していません。

たとえば、Microsoft Word 文書で作業しているときに、<kbd>Shift</kbd> キーを押したまま <kbd>"</kbd> を入力すると、Microsoft Word により、`"` 文字がスマート クォートに相当する `“` 文字にただちに置き換えられることに気づくことがあります。

| Description        | Unicode  | スマート クォート | 置換 |
|--------------------|----------|-------------|-------------|
| 左二重引用符  | `\u201c` | `“`         | `"`         |
| 右二重引用符 | `\u201d` | `”`         | `"`         |
| 左一重引用符  | `\u2018` | `‘`         | `'`         |
| 右一重引用符 | `\u2019` | `’`         | `'`         |

Markdown (" *\*.md*") ファイルでは、テキストを貼り付ける場合、またはコンテンツを更新する場合、この機能は、コンテンツをアクティブに評価し、それに応じて値を自動的に置き換えます。

> [!NOTE]
> スマート クォートの置換機能では、この他の文字も置き換えられます。たとえば、`©, ™, ®, •`、サブスクリプト文字、下付き文字、上付き文字などがありますが、この限りではありません。 これは、Word 文書のテキストを貼り付ける場合に有用です。

## <a name="preferences"></a>基本設定

この機能はオプションですが、既定値は `true` です。 この機能をオンまたはオフに切り替えるには、次の操作を行います。

1. **[ファイル]**  >  **[基本設定]**  >  **[設定]** の順に選択し、"*Docs Markdown Extension*" でフィルター処理します。
1. **[Markdown: Replace Smart Quotes]\(マークダウン: スマート クォートの置換\)** セクションの設定を切り替えます。

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![スマート クォートの置換のデモ](media/replace-smart-quotes.gif)](media/replace-smart-quotes.gif#lightbox)
