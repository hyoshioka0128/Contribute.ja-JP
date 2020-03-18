---
title: Visual Studio Code 用の Docs Authoring Pack
description: この記事では、docs.microsoft.com の Markdown の作成を促進する Visual Studio Code 拡張パックについて説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: meganbradley
ms.author: mbradley
ms.date: 03/05/2020
ms.openlocfilehash: 5bbf51af52069d5636715ffb2bd3f59bf459d5b9
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336379"
---
# <a name="docs-authoring-pack-for-vs-code"></a>VS Code 用 Docs Authoring Pack

Docs Authoring Pack は、docs.microsoft.com の Markdown の作成を支援する VS Code 拡張機能の集まりです。 このパックは、[VS Code Marketplace で入手可能であり](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)、次の拡張機能を含んでいます。

> [!div class="checklist"]
> * [Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown): docs.microsoft.com (Docs) コンテンツの Markdown 作成サポートを提供します。基本的な Markdown のサポートとカスタム Markdown 構文 (アラート、コード スニペット、ローカライズ不可テキストなど) のサポートが含まれます。 また、TOC エントリの挿入など、基本的な YAML の作成に関するサポートも追加されました。
> * [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint): David Anson による人気の Markdown リンターで、作成した Markdown が有効であることを確認できます。
> * [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): Street Side Software による、完全にオフラインのスペル チェック機能です。
> * [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): より正確な Markdown プレビューのために、docs.microsoft.com の CSS を使用します (カスタムのマークダウンを含む)。
> * [Docs Article Templates](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): ユーザーが、学習モジュールをスキャフォールディングし、Markdown の骨組みとなるコンテンツを新しいファイルに適用できるようになります。
> * [Docs YAML](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-yaml):Docs YAML スキーマ検証とオートコンプリートを提供します。
> * [ドキュメント イメージ](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-images):docs.microsoft.com の作成者を支援するために、フォルダーおよび個々のファイルのイメージ圧縮とサイズ変更を提供します。

## <a name="prerequisites-and-assumptions"></a>前提条件

Docs Markdown 拡張機能を使用して、相対リンク、画像、その他の埋め込みコンテンツを挿入するには、複製した Open Publishing System (OPS) リポジトリのルートを対象範囲とする VS Code ワークスペースが必要です。 たとえば、ドキュメント リポジトリを `C:\git\SomeDocsRepo\` に複製した場合は、VS Code でそのフォルダーまたはサブフォルダーを開きます。 **[ファイル]**  >  **[フォルダーを開く]** メニューを選択するか、コマンド ラインに `code C:\git\SomeDocsRepo\` を入力します。

アラートやスニペットなどの拡張機能でサポートされる一部の構文は、OPS のカスタム Markdown です。 カスタム Markdown は、OPS から公開しない限り正しくレンダリングされません。

## <a name="how-to-use-the-docs-markdown-extension"></a>Docs Markdown 拡張機能の使用方法

**Docs Markdown** のメニューにアクセスするには、<kbd>ALT+M</kbd> を入力します。 上矢印と下矢印をクリックまたは使用して、目的のコマンドを選択できます。 または、入力してフィルター処理を開始し、メニュー内の目的の機能が強調表示されたら <kbd>Enter</kbd> キーを押します。

コマンドの最新の一覧については、[Docs Markdown の説明](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown)を参照してください。

## <a name="how-to-generate-a-master-redirect-file"></a>マスター リダイレクト ファイルを作成する方法

Docs Markdown 拡張機能には、個々のファイルの `redirect_url` メタデータに基づいて、リポジトリのマスター リダイレクト ファイルを作成または更新するスクリプトが含まれています。 このスクリプトは、`redirect_url` についてリポジトリ内のすべての Markdown ファイルをチェックし、リポジトリのマスター リダイレクト ファイル ( *.openpublishing.redirection.json*) にリダイレクト メタデータを追加して、リダイレクトされたファイルをリポジトリ外部のフォルダーに移動します。 スクリプトを実行するには、次のようにします。

1. <kbd>F1</kbd> を選択して、VS Code コマンド パレットを開きます。
2. 入力を開始します: 「Docs:Generate...」
3. コマンド `Docs: Generate master redirection file` を選択します。
4. スクリプトの実行が完了すると、VS Code 出力ウィンドウにリダイレクトの結果が表示され、削除された Markdown ファイルが、既定のパスの下にある Docs Authoring\redirects フォルダーに追加されます。
5. 結果を確認します。 予想どおりの場合は、プル要求を送信してリポジトリを更新します。

## <a name="how-to-assign-keyboard-shortcuts"></a>キーボード ショートカットの割り当て方法

1. <kbd>CTRL+K</kbd>、<kbd>Ctrl+S</kbd> を入力しして、**キーボード ショートカット**の一覧を開きます。
1. カスタム キー バインドを作成するコマンド (`formatBold` など) を検索します。
1. マウス ポインターを行の上に置いたときにコマンド名の近くに表示されるプラス記号をクリックします。
1. 新しい入力ボックスが表示されたら、特定のコマンドにバインドするキーボード ショートカットを入力します。 たとえば、太字の共通のショートカットを使用するには、<kbd>Ctrl+B</kbd> を入力します。
1. Markdown 以外のファイルで使用できないようにするために、`when` 句をキー バインドに含めることをお勧めします。 これを行うには、*keybindings.json* を開き、コマンド名の下に次の行を挿入します (必ず行の間にコマンドを追加してください)。

    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    *keybindings.json* 内の完成したキー バインドは次のようになります。

    ```json
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

    > [!TIP]
    > このファイルにキー バインドを配置して、既定値を上書きします

1. *keybindings.json* を保存します。

キー バインドの詳細については、[VS Code のドキュメント](https://code.visualstudio.com/docs/getstarted/keybindings)を参照してください。

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>レガシーの "Gauntlet" ツールバーの表示方法

"Gauntlet" という名前の拡張コードの以前のユーザーは、Docs Markdown 拡張機能がインストールされたときに VS Code ウィンドウの下部にオーサリング ツールバーが表示されなくなったことに気付くでしょう。 これは、このツールバーが VS Code ステータス バーの大きなスペースを占有し、拡張機能のユーザー エクスペリエンスのベスト プラクティスに従っていなかったため、新しい拡張機能で非推奨になったからです。 しかし、オプションで VS Code の settings.json ファイルを次のように更新することでツールバーを表示できます。

1. VS Code で、 **[ファイル]**  >  **[基本設定]**  >  **[設定]** を選択するか、<kbd>Ctrl+,</kbd> を選択します。
1. **[ユーザー設定]** を選択してすべての VS Code ワークスペースの設定を変更するか、 **[ワークスペースの設定]** を選択して現在のワークスペースのみの設定を変更します。
1. **[拡張機能]**  >  **[Docs Markdown Extension Configuration]** (Docs Markdown 拡張機能の構成) を選択し、 **[Show the legacy toolbar in the bottom status bar]** (下のステータス バーにレガシ ツールバーを表示する) を選択します。

   ![VS Code にレガシ ツールバー表示する](docs-authoring/media/show-gauntlet-bar.png)

選択が完了すると、VS Code によって *settings.json* ファイルが更新されます。 変更を有効にするために、ウィンドウの再読み込みを求めるメッセージが表示されます。

拡張機能に追加された新しいコマンドは、ツールバーからは使用できません。

## <a name="how-to-use-docs-templates"></a>Docs テンプレートを使用する方法

Docs Article Templates 拡張機能を使用すると、VS Code 内の作成者は一元的なストアから Markdown テンプレートを取得して、これをファイルに適用することができます。 テンプレートは、記事に必須メタデータが含まれていること、コンテンツの標準に従っていることなどを確実にするのに役立ちます。 テンプレートは、パブリック GitHub リポジトリ内で Markdown ファイルとして管理されます。

### <a name="to-apply-a-template-in-vs-code"></a>VS Code でテンプレートを適用する

1. 確実に Docs Article Templates 拡張機能がインストールされ、有効になっているようにします。
1. Docs Markdown 拡張機能がインストールされていない場合は、<kbd>F1</kbd> をクリックしてコマンド パレットを開き、「template」と入力してフィルター処理を行った後、`Docs: Template` をクリックします。 Docs Markdown 拡張機能がインストールされている場合は、コマンド パレットを使用するか <kbd>Alt+M</kbd> をクリックして Docs Markdown QuickPick メニューを表示した後、一覧から `Template` を選択します。
1. 表示される一覧から必要なテンプレートを選択します。

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>VS Code の設定に GitHub ID や Microsoft のエイリアスを追加する

Templates 拡張機能では、3 つの動的メタデータ フィールド (author、ms.author、ms.date) がサポートされます。 つまり、テンプレートの作成者が Markdown テンプレートのメタデータ ヘッダー内でこれらのフィールドを使用している場合、以下のように、テンプレートを適用するときにこれらが自動でファイルに追加されます。

| メタデータ フィールド | 値 |
|--|--|
| `author` | GitHub エイリアス (VS Code の設定ファイルに指定した場合)。 |
| `ms.author` | Microsoft のエイリアス (VS Code の設定ファイルで指定している場合)。 Microsoft の従業員ではない場合は、未指定のままにします。 |
| `ms.date` | 現在の日付 (Docs サポート形式 `MM/DD/YYYY`)。 後でファイルを更新しても、この日付は自動的に更新されません。手動で更新する必要があります。 このフィールドは、"記事の新しさ" を示すために使用されます。 |

### <a name="to-set-author-andor-msauthor"></a>author または ms.author を設定するには

1. VS Code で、 **[ファイル]**  >  **[基本設定]**  >  **[設定]** を選択するか、<kbd>Ctrl+,</kbd> を選択します。
1. **[ユーザー設定]** を選択してすべての VS Code ワークスペースの設定を変更するか、 **[ワークスペースの設定]** を選択して現在のワークスペースのみの設定を変更します。
1. 左側の [既定の設定] ウィンドウで **[Docs Article Templates Extension Configuration]** (Docs Markdown 拡張機能の構成) を見つけ、必要な設定の横にある鉛筆アイコンをクリックしてから、[設定を置換] をクリックします。
1. **[ユーザー設定]** ウィンドウが横に並んで開き、新しいエントリが下部に表示されます。
1. GitHub ID または Microsoft メール エイリアスを必要に応じて追加し、ファイルを保存します。
1. 変更を有効にするには、VS Code を閉じてから再起動する必要がある場合があります。
1. これで、動的フィールドを使用するテンプレートを適用したときに、GitHub ID や Microsoft のエイリアスが自動でメタデータ ヘッダーに追加されるようになりました。

### <a name="to-make-a-new-template-available-in-vs-code"></a>VS Code で新しいテンプレートを使用できるようにするには

1. テンプレートを Markdown ファイルとしてドラフトします。
1. [MicrosoftDocs/content-templates](https://github.com/MicrosoftDocs/content-templates) リポジトリの templates フォルダーへのプル要求を送信します。

docs.microsoft.com チームがテンプレートを確認し、docs.microsoft.com スタイルガイド ラインを満たしている場合に PR をマージします。 マージされると、このテンプレートは、Docs Article Templates 拡張機能のすべてのユーザーが使用できるようになります。

## <a name="demo-several-features"></a>いくつかの機能のデモ

以下は、Docs Authoring Pack の次の機能を説明する短いビデオです。

* **YAML ファイル**
  * "Docs:Link to file in repo" のサポート
* **Markdown ファイル**
  * "ms.date" メタデータ値のコンテキスト メニューオプションの更新
  * コードフェンス言語識別子のコード オートコンプリート サポート
  * 認識されないコードフェンス言語識別子の警告、自動修正のサポート
  * 選択範囲を昇順に並べ替え (A から Z)
  * 選択範囲を降順に並べ替え (Z から A)

> [!VIDEO https://www.youtube.com/embed/6zfbBRdjlw8]

## <a name="contribution-expectations"></a>コントリビューションの見込み

Docs Authoring Pack 拡張機能はオープンソースであり、GitHub アカウントを持っていればだれでもコントリビュートできます。 Microsoft 社内にこのプロジェクトに積極的に取り組んでいる専属チームがあります。 このチームは、問題とプル要求を監視します。 サービス レベル アグリーメント (SLA)、プル要求のレビュー終了見込みは、現在 1 週間です。 チームでは、この所要時間を改善するために、自動化の取り組みを進めています。

## <a name="next-steps"></a>次の手順

Visual Studio Code 拡張機能である Docs Authoring Pack に用意されているさまざまな機能について説明します。

* [開発言語の完了](docs-authoring/dev-lang-completion.md)
* [画像の圧縮](docs-authoring/image-compression.md)
* [メタデータの更新](docs-authoring/metadata-updates.md)
* [テーブルの再フォーマット](docs-authoring/reformat-table.md)
* [スマート クォートの置換](docs-authoring/smart-quote-replacement.md)
* [並べ替えリダイレクト](docs-authoring/sort-redirects.md)
* [選択範囲の並べ替え](docs-authoring/sort-selection.md)
