---
title: Visual Studio Code 用の Docs Authoring Pack
description: この記事では、docs.microsoft.com の Markdown の作成を促進する Visual Studio Code 拡張パックについて説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: meganbradley
ms.author: mbradley
ms.date: 10/22/2018
ms.openlocfilehash: 11f18ce4f769b478108d399b780937f927e0e12d
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72288332"
---
# <a name="docs-authoring-pack-for-vs-code"></a>VS Code 用 Docs Authoring Pack

Docs Authoring Pack は、docs.microsoft.com の Markdown の作成を支援する Visual Studio Code 拡張機能の集まりです。 このパックは、[VS Code Marketplace で入手可能であり](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)、次の拡張機能を含んでいます。

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint): David Anson 氏による人気のある Markdown リンターで、ベスト プラクティスに従った Markdown を作成するために役立ちます。
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): Street Side Software による、完全にオフラインのスペル チェック機能です。
- [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): より正確な Markdown プレビューのために、docs.microsoft.com の CSS を使用します (カスタムのマークダウンを含む)。
- [Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown): Open Publishing System (OPS) での docs.microsoft.com コンテンツの Markdown 作成サポートを提供します。OPS での基本的な Markdown のサポートとカスタム Markdown 構文のサポートが含まれます。 このトピックの残りの部分では、Docs Markdown の拡張機能について説明します。
- [Docs Article Templates](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): ユーザーが、Markdown の骨組みとなる内容を新しいファイルに適用できるようになります。

## <a name="prerequisites-and-assumptions"></a>前提条件

Docs Markdown 拡張機能を使用して、相対リンク、画像、その他の埋め込みコンテンツを正確に挿入するには、複製された Open Publishing System (OPS) リポジトリのルートを対象範囲とした VS Code ワークスペースを持っている必要があります。

アラートやスニペットなどの拡張機能でサポートされる一部の構文は、OPS のカスタム Markdown であり、OPS を介して公開されない限り正しくレンダリングされません。

## <a name="how-to-use-the-docs-markdown-extension"></a>Docs Markdown 拡張機能の使用方法

Docs Markdown のメニューにアクセスするには、「`ALT+M`」と入力します。 上下の矢印をクリックまたは使用して、必要な機能を選択するか、フィルターの入力して開始し、メニューで必要な機能が強調表示されたら `ENTER` キーを押します。 次の機能を使用できます:

|機能     |Description           |
|-------------|----------------------|
|プレビュー      |Docs Preview 拡張機能を使用し、左右に並べたウィンドウにアクティブなトピックのプレビューを表示します。 このオプションは、Docs Preview がインストールされている場合のみ利用可能です。|
|太字         |テキストを**太字**に書式設定します。|
|斜体       |テキストを*斜体*に書式設定します。|
|コード         |1 つ以下の線が選択されているときに、テキストを `inline code` として書式設定します。<br><br>複数の線が選択されている場合、それらをフェンスされたコードのブロックとして書式設定します。オプションで OPS でサポートされているプログラミング言語を選択できます。|
|アラート        |メモ、重要、警告、またはヒントを挿入します。<br><br>メニューからアラートを選択し、アラートの種類を選択します。 以前にテキストを選択している場合は、選択したアラートの構文でテキストが囲まれます。 テキストを選択していない場合は、プレースホルダーのテキストと共にアラートが追加されます。|
|番号付きリスト|新しい番号付きリストを挿入します。<br><br> 複数の行が選択されている場合は、各行がリスト項目になります。 Markdown 内の番号付きリストはすべて 1 として表示されますが、docs.microsoft.com では連番、または入れ子になったリストでは文字としてレンダリングされます。 入れ子になった番号付きリストを作成するには、親リスト内からタブを指定します。|
|箇条書き|新しい箇条書きを挿入します。|
|テーブル        |Markdown のテーブル構造を挿入します。<br><br>テーブル コマンドを選択した後で、3:4 のように列:行の形式で列と行の数を指定します。 この式で指定できる列の最大数は 5 です。読みやすくするためにこの最大数が推奨されます。|
|リポジトリ内のファイルへのリンク|現在のリポジトリ内の別のファイルへの相対リンクを挿入します。 このオプションを選択した後で、コマンド ウィンドウに入力し、名前でフィルター処理し、必要なファイルを選択します。 前にテキストを選択した場合、これはリンク テキストとなります。 そうでない場合、対象ファイルの H1 がリンク テキストとして使用されます。|
|Web ページへのリンク    |Web ページへのリンクを挿入します。 このオプションを選択した後、コマンド ウィンドウに URI を貼り付けるか入力します。 `https://` は必須です。 前にテキストを選択した場合、これはリンク テキストとなります。 そうでない場合、URI がリンク テキストとして使用されます。|
|見出しへのリンク     |現在のファイルまたはリポジトリ内の別のファイル内のブックマークにリンクします。<br>`Bookmark in this file`:　現在のファイルの見出しの一覧から選択し、適切に書式設定されたブックマークを挿入します。<br>`Bookmark in another file`:　最初に、ファイル名でフィルター処理して、リンク先のファイルを選択し、次に選択したファイル内の適切な見出しを選択します。|
|イメージ        |代替テキスト (アクセシビリティのために必要) を入力してそれを選択し、このコマンドを実行してリポジトリ内のサポートされる画像ファイルのリストをフィルター処理し、必要なファイルを選択します。 このコマンドを呼び出したときに代替テキストを選択していない場合、画像ファイルを選択する前に代替テキストを選択するように指示されます。|
|含める      |現在のファイル内に埋め込むファイルを見つけます。|
|スニペット      |現在のファイル内に埋め込むリポジトリ内のコード スニペットを見つけます。|
|ビデオ        |埋め込みビデオを追加します。|
|テンプレート     |新しいファイルを作成し、Markdown テンプレートを適用します。 詳細については、以下の「[テンプレート](#how-to-use-docs-templates)」をご覧ください。|

## <a name="how-to-assign-keyboard-shortcuts"></a>キーボード ショートカットの割り当て方法

1. 「`CTRL+K`」と入力し、「`CTRL+S`」と入力してキーボード ショートカットの一覧を開きます。
1. カスタム キーバインドを作成するコマンド (`formatBold` など) を検索します。
1. マウス ポインターを行の上に置いたときにコマンド名の近くに表示されるプラス記号をクリックします。
1. 新しい入力ボックスが表示されたら、特定のコマンドにバインドするキーボード ショートカットを入力します。 たとえば、太字の共通のショートカットを使用するには、「`ctrl+b`」と入力します。
1. Markdown 以外のファイルで使用できないようにするために、`when` 句をキーバインドに含めることをお勧めします。 これを行うには、*keybindings.json* を開き、コマンド名の下に次の行を挿入します (必ず行の間にコマンドを追加してください)。
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    keybindings.json 内の完成したキーバインドは次のようになります。

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. keybindings.json を保存します。

詳細については、VS Code のドキュメントの[キーバインド](https://code.visualstudio.com/docs/getstarted/keybindings)を参照してください。

## <a name="how-to-show-the-legacy-toolbar"></a>従来のツール バーを表示する方法

プレリリース バージョンの拡張機能のユーザーは、Docs Markdown 拡張機能がインストールされたときに VS Code ウィンドウの下部にオーサリング ツールバーが表示されなくなったことに気付くでしょう。 これは、ツールバーが VS Code ステータス バー上で多くの領域を使用し、拡張機能のユーザー エクスペリエンスのベスト プラクティスに従っていなかったために新しい拡張機能で非推奨になったためです。 しかし、オプションで VS Code の settings.json ファイルを次のように更新することでツールバーを表示できます。

1. VS Code で、[ファイル]、[基本設定]、[設定]、 (`CTRL+Comma`) の順に選択します。
1. [ユーザー設定] を選択してすべての VS Code ワークスペースの設定を変更するか、[ワークスペースの設定] を選択して、現在のワークスペースのみの設定を変更します。
1. [既定の設定] ウィンドウで、[Docs Authoring Extension Configuration]\(Docs Authoring 拡張機能の構成\) を見つけ、目的の設定の横にある鉛筆アイコンを選択します。 次に、`true` または `false` を選択するように指示されます。 選択すると、VS Code によって settings.json ファイルに自動的に値が追加され、変更を有効にするためにウィンドウを再び読み込むように指示されます。

## <a name="how-to-use-docs-templates"></a>Docs テンプレートを使用する方法

Docs Article Templates 拡張機能を使用すると、VS Code 内の作成者は一元的なストアから Markdown テンプレートを取得して、これをファイルに適用することができます。 テンプレートは、記事に必須メタデータが含まれていること、コンテンツの標準に従っていることなどを確実にするのに役立ちます。 テンプレートは、パブリック GitHub リポジトリ内で Markdown ファイルとして管理されます。

### <a name="to-apply-a-template-in-vs-code"></a>VS Code でテンプレートを適用する

1. Docs Markdown 拡張機能をインストールしていない場合は、F1 キーを押してコマンド パレットを開き、「template」と入力してフィルター処理を行った後、`Docs: Template` をクリックします。 Docs Markdown 拡張機能をインストールしている場合は、コマンド パレットを使用するか `Alt+M` をクリックして Docs Markdown QuickPick メニューを表示した後、一覧から `Template` を選択します。
1. 表示される一覧から必要なテンプレートを選択します。

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>VS Code の設定に GitHub ID や Microsoft のエイリアスを追加する

Templates 拡張機能では、3 つの動的メタデータ フィールド (author、ms.author、ms.date) がサポートされます。 つまり、テンプレートの作成者が Markdown テンプレートのメタデータ ヘッダー内でこれらのフィールドを使用している場合、以下のように、テンプレートを適用するときにこれらが自動でファイルに追加されます。

|メタデータ  |値|
|----------|---------------|
|author    |GitHub ID (VS Code の設定ファイルで指定している場合)。|
|ms.author |Microsoft のエイリアス (VS Code の設定ファイルで指定している場合)。 Microsoft の従業員ではない場合は、指定しないままにします。|
|ms.date   |Docs サポート形式 (MM/DD/YYYY) での現在の日付。 後でファイルを更新する場合、日付は自動的に更新されないことにご注意ください。 docs.microsoft.com サイトでの最も新しい発行日を示すように ms.date 値を手動で更新する必要があります。|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>author (GitHub ID) や ms.author (Microsoft のエイリアス) を設定する

1. VS Code で、[ファイル]、[基本設定]、[設定]、 (`CTRL+Comma`) の順に選択します。
1. [ユーザー設定] を選択してすべての VS Code ワークスペースの設定を変更するか、[ワークスペースの設定] を選択して、現在のワークスペースのみの設定を変更します。
1. 左側の [既定の設定] ウィンドウから Docs Article Templates の拡張機能の構成を探して、必要な設定の横にある鉛筆アイコンをクリックした後、[設定を置換] をクリックします。
1. [ユーザー設定] ウィンドウが横に並べて開かれ、新しいエントリが下部に表示されます。
1. GitHub ID または Microsoft メール エイリアスを必要に応じて追加し、ファイルを保存します。
1. 変更を有効にするには、VS Code を閉じてから再起動する必要がある場合があります。
1. これで、動的フィールドを使用するテンプレートを適用したときに、GitHub ID や Microsoft のエイリアスが自動でメタデータ ヘッダーに追加されるようになりました。
