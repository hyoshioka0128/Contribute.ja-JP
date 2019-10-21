---
title: コンテンツ オーサリング ツールのインストール
description: この記事は、Git、および Markdown ファイルの編集に必要なクライアント ツールのダウンロードとインストールに役立ちます。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: jasonwhowell
ms.author: jasonh
ms.date: 04/30/2018
ms.openlocfilehash: 24d47c4e094c318be75a27dbaaec11d8ead94452
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72288559"
---
# <a name="install-content-authoring-tools"></a>コンテンツ オーサリング ツールのインストール

この記事では、Git クライアント ツールと Visual Studio Code を対話形式でインストールする手順について説明します。
> [!div class="checklist"]
> * [Git](https://git-scm.com/) をインストールする
> * [Visual Studio Code](https://code.visualstudio.com/) をインストールする
> * [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) をインストールする

>[!IMPORTANT]
> 記事に軽微な変更しか加えていない場合は、この記事の手順を実行する必要は*ない*ため、直接[簡易な変更のワークフロー](index.md#quick-edits-to-existing-documents)に進めます。
>
> 大規模な変更を行う共同作成者は、これらの手順を実行することをお勧めします。そうすることで、[大規模/長期間の変更のワークフロー](how-to-write-workflows-major.md)を使用できるようになります。 メイン リポジトリで書き込みアクセス許可を持っている場合でも、"*リポジトリのフォークと複製を行うことを強くお勧めします (本ガイドでもそれを前提としています)* "。それにより、予定している変更をフォークに保存するための読み取り/書き込み権限が付与されます。

## <a name="install-git-client-tools"></a>Git クライアント ツールのインストール 

 プラットフォーム用の [Software Freedom Conservancy の Git クライアント ツール](https://git-scm.com/download/)の最新バージョンをインストールします。 

* [Git for Windows](https://git-scm.com/download/win)。 このインストールには、Git バージョン管理システムや、ローカル Git リポジトリとの対話で使用するコマンドライン アプリである Git Bash が含まれます。
* Mac 用の Git は Xcode コマンド ライン ツールの一部として提供されます。 コマンド ラインから単純に `git` を実行します。 必要に応じて、コマンド ライン ツールのインストールを求められます。 また、Software Freedom Conservancy から [Mac 用の Git](https://git-scm.com/download/mac) をダウンロードすることもできます。
* [Linux と Unix 用の Git](https://git-scm.com/download/linux)

コマンド ライン インターフェイス (CLI) ではなくグラフィカル ユーザー インターフェイス (GUI) を使用する場合は、[Software Freedom Conservancy の使用可能な GUI クライアントに関するページ](https://git-scm.com/downloads/guis)、[GitHub の GitHub デスクトップ](https://desktop.github.com/)に関するページ、[Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) のページで、一部の一般的なオプションを確認してください。

選択したクライアントについてインストールと構成の手順に従います。

次の記事では、[ローカル Git リポジトリを設定](get-started-setup-local.md)します。

   その他の Git リソースについては、こちらを参照してください: [Git 用語集](https://help.github.com/articles/github-glossary) | [Git の基礎](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Git および GitHub の学習](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>Markdown エディターについて

Markdown は、読みやすく、かつ習得しやすい軽量のマークアップ言語です。 そのため、急速に業界標準になりました。 Markdown で記事を書くには、まず、Markdown エディターをダウンロードしてインストールすることをお勧めします。  [Visual Studio Code](https://code.visualstudio.com/) は、Markdown を編集するために Microsoft が推奨しているツールです。 [Atom](https://atom.io) も、Markdown を編集するための一般的なツールです。

Markdown テキストは、.md 拡張子の付いたファイルに保存されます。

Markdown の基本と Open Publishing Services (OPS) による Markdown のカスタム拡張機能でサポートされる機能を含む、Markdown での記述方法の詳細については、「[ドキュメントを記述するための Markdown の使用方法](how-to-write-use-markdown.md)」と「[OPS の Markdown 参照](markdown-reference.md)」の記事で説明します。

## <a name="visual-studio-code"></a>Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/) は Windows、Linux、Mac で動作する軽量のエディターで、VS Code とも呼ばれます。 これには、git 統合と拡張機能のサポートが含まれています。

[VS Code](https://code.visualstudio.com/) をダウンロードしてインストールします。 VS Code のホーム ページでは、オペレーティング システムが正しく検出されます。

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> VS Code を起動し、現在のフォルダーを開き、コマンド ラインまたは bash シェルで `code .` コマンドを実行します。 現在のフォルダーがローカル git リポジトリの一部である場合は、GitHub 統合が Visual Studio Code に自動的に表示されます。

## <a name="docs-authoring-pack"></a>Docs Authoring Pack
Visual Studio Code 用に Docs Authoring Pack をインストールします。 この一連の拡張機能には、Markdown の記述に役立つ基本的な作成サポートやプレビュー機能が含まれているため、docs.microsoft.com サイトのスタイルで Markdown がどのように表示されるかを確認できます。

   この [Marketplace ページ](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)にアクセスして **[インストール]** を選択するか、VS Code ウィンドウの拡張機能の一覧で `docsmsft.docs-authoring-pack` を検索します。 

   Docs Authoring Pack にアクセスするには、VS Code 内で Alt+M を押します。 ツール バーは既定で非表示ですが、表示できます。 VS Code の設定を編集し (Ctrl+コンマ)、ユーザー設定 `"markdown.showToolbar": true` を追加して、ツール バーを表示します。

   詳しくは、[Docs Authoring Pack](how-to-write-docs-auth-pack.md) に関するページを参照してください。


## <a name="next-steps"></a>次のステップ

これで、[ローカル Git リポジトリを設定](get-started-setup-local.md)する準備が整いました。
