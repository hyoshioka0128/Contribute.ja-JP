---
title: 開発言語の完了 - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack で、開発言語の完了が共同作成者をどのように支援するかについて説明します。
author: scottaddie
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: scaddie
ms.openlocfilehash: f81dc2315dc09256639c98ed72484517ff2c6ff3
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336798"
---
# <a name="dev-lang-completion"></a>開発言語の完了

[!INCLUDE [markdown-extension](includes/markdown-extension.md)]

## <a name="summary"></a>サマリー

共同作成者は、Markdown ファイルでトリプルバッククォート (コード フェンスの始まり) の後に続けることができる有効な言語識別子 (開発言語) を決定するための支援を必要とします。 残念ながら、開発言語のビルド時検証機能はありません。 その結果、同じ概念 docset 内で単一の言語が異なって表現されています。

例として、C# について考えてみましょう。 共同作成者は、言語の開発言語表現として `c#`、`C#`、`cs`、`csharp` を使用しています。 これらの表現のうち、正しいのはどれでしょうか?

"*開発言語の完了*" 機能は、既知の dev lang の一覧を表示することにより、混乱を解消します。 IntelliSense から開発言語名を選択すると、次のようになります。

* コード フェンスは閉じられます。
* カレットは、コード フェンス内に配置されます。

## <a name="preferences"></a>基本設定

この機能を無効にすることはできません。 次の設定を使用できます。

* [[Display commonly used dev langs]\(一般的に使用されている開発言語を表示する\)](#display-commonly-used-dev-langs)
* [[Display all known dev langs]\(既知のすべての開発言語を表示する\)](#display-all-known-dev-langs)

### <a name="display-commonly-used-dev-langs"></a>一般的に使用されている開発言語を表示する

単一の docset で、有効な開発言語のサブセットのみが使用されます。 ユーザー エクスペリエンスを向上するには、次の操作を行います。

1. Visual Studio Code で、ルート ディレクトリに相対的な docset を開きます。
1. **[ファイル]**  >  **[基本設定]**  >  **[設定]** の順に選択し、"*Docs Markdown Extension*" でフィルター処理します。
1. **[Markdown: Docset Languages]\(Markdown: docset の言語\)** セクションの **[settings.json で編集]** をクリックします。
1. 次の `markdown.docsetLanguages` プロパティを "*settings.json*" ファイルに追加します。

    ```json
    {
        "markdown.docsetLanguages": [

        ]
    }
    ```

1. プロパティの空の配列にカレットを位置付け、IntelliSense をアクティブにします (<kbd>Ctrl</kbd> + <kbd>Space</kbd> キーを押します)。 既知の開発言語名の一覧が表示されます。
1. 満足できる一覧になるまで、開発言語名を配列に追加します。 たとえば、次の一覧では、ユーザーがトリプルクォートを入力した後、4 つの開発言語が表示されます。

    ```json
    {
        "markdown.docsetLanguages": [
            ".NET Core CLI",
            "C#",
            "Markdown",
            "YAML"
        ]
    }
    ```

1. "*settings.json*" ファイルの変更を保存します。

> [!WARNING]
> `markdown.docsetLanguages` 配列が空の場合、既知のすべての開発言語が表示されます。

### <a name="display-all-known-dev-langs"></a>既知のすべての開発言語を表示する

既定では、既知のすべての開発言語名が IntelliSense に表示されます。 この設定は、「[一般的に使用されている開発言語を表示する](#display-commonly-used-dev-langs)」で説明した `markdown.docsetLanguages` プロパティをオーバーライドします。

この設定を変更するには、次の操作を行います。

1. **[ファイル]**  >  **[基本設定]**  >  **[設定]** の順に選択し、"*Docs Markdown Extension*" でフィルター処理します。
1. **[Markdown: All Available Languages]\(Markdown: 使用可能なすべての言語\)** セクションの設定を切り替えます。

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![開発言語の完了](media/dev-lang-completion.gif)](media/dev-lang-completion.gif#lightbox)
