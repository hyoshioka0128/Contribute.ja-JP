---
title: メタデータの更新 - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack からメタデータを更新する方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: 391ea6c523d1f1b82b21883cea5e3428e86633e9
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336637"
---
# <a name="update-metadata"></a>メタデータの更新

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

Markdown (" *\*.md*") ファイルには、メタデータ固有の 2 つのコンテキスト メニュー項目があります。 テキスト エディター内の任意の場所を右クリックすると、次のようなメニュー項目が表示されます。

:::image type="content" source="media/update-metadata-menu.png" alt-text="メタデータの更新コンテキスト メニュー":::

## <a name="update-msdate-metadata-value"></a>`ms.date` メタデータ値の更新

**[Update `ms.date` Metadata Value]\(ms.date メタデータ値の更新\)** オプションを選択すると、Markdown ファイルの現在の `ms.date` 値が今日の日付に設定されます。 ドキュメントに `ms.date` メタデータ フィールドがない場合、アクションは実行されません。

## <a name="update-implicit-metadata-values"></a>暗黙的なメタデータ値の更新

**[Update implicit metadata values]\(暗黙的なメタデータ値の更新\)** オプションを選択すると、暗黙的に指定できるすべてのメタデータ値が検索され、置き換えられます。 メタデータ値は、"*docfx.json*" ファイルの `build/fileMetadata` ノードの下に暗黙的に指定されます。 `fileMetadata` ノード内の各キーと値のペアは、メタデータの既定値を表します。 たとえば、"*最上位レベル/サブフォルダー*" ディレクトリ内にある Markdown ファイルで、`ms.author` メタデータ値を省略すると、`fileMetadata` ノードで使用する既定値が暗黙的に指定される可能性があります。

```json
{
    "build": {
        "fileMetadata": {
            "ms.author": {
                "top-level/sub-folder/**/**.md": "dapine"
            }
        }
    }
}
```

この場合、すべての Markdown ファイルで、`ms.author: dapine` メタデータ値が暗黙的に使用されます。 この機能は、"*docfx.json*" ファイル内で見つかったこのような暗黙的な設定に対して動作します。 Markdown ファイルに、暗黙の値以外の値が明示的に設定されたメタデータが含まれている場合、それらはオーバーライドされます。

次の Markdown ファイルのメタデータについて考えてみましょう。この Markdown ファイルは**最上位レベル/サブフォルダー/includes/example.md** 内にあります。

```markdown
---
ms.author: someone-else
---

# Content
```

"*docfx.json*" が上記の内容であることを前提にすると、このファイルに対して **[暗黙的なメタデータ値の更新]** オプションが実行されると、メタデータ値は `ms.author: dapine` に更新されます。

```markdown
---
ms.author: dapine
---

# Content
```

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![メタデータの更新のデモ](media/update-metadata.gif)](media/update-metadata.gif#lightbox)
