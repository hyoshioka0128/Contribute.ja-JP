---
title: PowerShell ドキュメント リポジトリへの協力プロセス
description: この記事では、PowerShell ドキュメント リポジトリへの協力方法について簡単に紹介します。 使用するリポジトリについて、コンテンツを整理するプロセスについて、さらにコード サンプルなどの資産を管理するためのポリシーについて説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: sdwheeler
ms.author: sewhee
ms.date: 10/07/2019
ms.openlocfilehash: 9802942dccbfad2cb860739ffba4b30d2b0af0c9
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72290198"
---
# <a name="process-for-contributing-to-powershell-docs"></a>PowerShell ドキュメントに協力するためのプロセス

ドキュメントに対するコミュニティの投稿に感謝します。PowerShell ドキュメントに協力する際に留意する必要がある適用規則のいくつかを次の一覧に示します。

- Microsoft が予期していない大量の pull request を**送信しないでください**。 Issue を提出してディスカッションを開始していただければ、長い時間が費やされる前に Microsoft はその目的に同意することができます。
- 次の手順と、[コード](powershell-style-code.md)と[リファレンス](powershell-style-reference.md)のスタイル ガイドに**従います**。
- ご自分の作業の出発点として**テンプレート ファイル**を[使用してください](powershell-style-basic-markdown.md)。
- 記事で作業する前に、使用するフォーク上に独立したブランチを**作成します**。
- [GitHub フロー ワークフロー](../how-to-write-workflows-major.md)に**従います**。
- ご自分の共同作成について頻繁にブログ投稿およびツイート (または同類の作業) を**行います**。

このようなガイドラインに従うことにより、ご自分にとっても Microsoft にとっても、より望ましいエクスペリエンスが確保されます。

## <a name="make-a-contribution-to-powershell-docs"></a>PowerShell ドキュメントに協力する

既存の[イシュー](https://github.com/MicrosoftDocs/PowerShell-Docs/issues/new/choose)から選択できます。
関心とコミットメントのレベルに応じて、取り組みは次のカテゴリに分けられます。

- **小さい変更**。 小さい変更の場合は、共同作成者ガイドの[ホーム ページ](../index.md#quick-edits-to-existing-documents)上で "GitHub での編集の手順" を参照してください。 小さな変更の例を次に示します。

  - 入力ミスおよびスペル ミスの修正
  - 文法または書式設定の改善
  - 技術または事実に関する軽微な編集

- **メンテナンス**。 このカテゴリには、壊れたリンクや誤ったリンクの修正、不足しているコード例の追加、限定されたコンテンツ Issue への対処など、比較的シンプルな共同作成が含まれています。 場合によって、これらの Issue は多数のファイルにかかわっている場合があります。 そのような場合は、始める前に、作業対象とするものを Microsoft に知らせてください。 Issue に対してコメントを追加することで、ご自分がその Issue で作業していることを Microsoft に伝えてください。

- **コンテンツの更新**。 発生するドキュメント セットは膨大であるため、コンテンツはすぐに古くなり、改訂が必要になります。 さらに、コンテンツによってはさまざまな理由で、複製されていたり、さらには正副 3 部目が複製されていたりします。 コンテンツの更新では、個々のトピックが機能領域において現在のコンテンツであるか、それとも改訂対象のコンテンツであるかを確認する必要があります。これにより、重複をなくし、すべての一意のコンテンツがよりコンパクトなドキュメント セットで確実に保持されるようにすることができます。

- **新しいコンテンツの作成**。 独自のトピックを作成することに関心がある場合は、これらの Issue を参照してください。Microsoft がドキュメントセットへの追加を望んでいることを自身で認めているトピックが一覧されています。 ただし、トピックに対して作業を開始する前に Microsoft にその旨をお知らせください。 ここに一覧されていないトピックの作成に関心がある場合は、Issue を開示してください。

作業するタスクを選択したら、[ファースト ステップ](../get-started-setup-github.md) ガイドに従って、GitHub アカウントを作成し、使用する環境を設定します。

### <a name="making-large-changes"></a>大きな変更を行う

**手順 1:** 新しいコンテンツの作成または既存のコンテンツの徹底的な改訂に関心がある場合は、ご自分が行いたい内容を説明するイシューを開示してください。

**手順 2:** `MicrosoftDocs/PowerShell-Docs` リポジトリをフォークし、変更のための作業ブランチを作成します。

**手順 3:** この新しいブランチで変更を加えます。

新しいトピックの場合は、開始点として[スタイル ガイド](powershell-style-basic-markdown.md)のテンプレートを使用します。 スタイル ガイドには執筆のガイドラインが記載されており、各記事に必要なメタデータについての説明があります。

手順 1 で決定したご自分の記事の TOC での場所に対応するフォルダーに移動します。
そのフォルダーには、そのセクションに属するすべての記事の Markdown ファイルが格納されています。 必要に応じて、ご自分のコンテンツのファイルを配置するフォルダーを新たに作成します。 そのセクションのメイン記事は、*index.md* と呼ばれます。
イメージなどの静的なリソースについては、ご自分の記事が格納されているフォルダー内に **media** というサブフォルダーを作成します (それがまだ作成されていない場合)。 **media** フォルダー内に、記事の名前を使用してサブフォルダーを作成します (ただし、インデックス ファイルは除く)。

適切な Markdown 構文に必ず従ってください。 詳細な手順と例については、[スタイル ガイド](powershell-style-basic-markdown.md)を参照してください。

**構造の例**

```
reference
  /docs-conceptual
    /learn
      /remoting
        managing-remote-sessions.md
        /images
          /managing-remote-sessions
            sesssion-list.png
```

**手順 4:** プル要求 (PR) を作業ブランチから*ステージング* ブランチに送信します。

通常、PR は一度に 1 つのイシューに対処する必要があります。 PR により、1 つまたは複数のファイルを変更することができます。 異なるそれぞれのファイル上で複数の修正に対処する場合、個別の PR が推奨されます。

ご自分の PR によって既存の Issue を修正する場合は、コミット メッセージまたは PR 記述に `Fixes #Issue_Number` キーワードを追加します。 これにより、その Issue は PR がマージされると、自動的に終了されます。 詳細については、[コミット メッセージを介した Issue の終了](https://help.github.com/articles/closing-issues-via-commit-messages/) に関するページを参照してください。

PowerShell チームが PR をレビューし、それを承認するために他の変更が必要かどうかをお知らせします。

**手順 5:** チームでディスカッションしたとおりに、ご自分のブランチに対して必要な更新を行います。

PR が承認されると、メンテナンス ツールが PR を*ステージング* ブランチにマージします。 *ステージング* ブランチのすべてのコミットは*ライブ* ブランチに定期的にプッシュされます。 投稿内容が公開されると、[PowerShell ドキュメント サイト](https://docs.microsoft.com/PowerShell/)で確認できます。 通常、1 週間に 2、3 回公開されます。

## <a name="contributor-license-agreement"></a>共同作成者使用許諾契約書

PR をマージする前に、[Contribution License Agreement (CLA)](https://cla.opensource.microsoft.com/MicrosoftDocs/PowerShell-Docs) に署名する必要があります。 これは、ドキュメントを共同作成するときの 1 回限りの要件です。

事前に契約書に署名しておく必要はありません。 通常どおり、ご自分の PR を複製、フォーク、送信することができます。
ご自分の PR が作成されたら、それを CLA ボットによって分類することができます。 変更が小さい場合 (たとえば、入力ミスの修正)、PR には `cla-not-required` というラベルが適用されます。 それ以外の場合は、`cla-required` として分類されます。 CLA に署名すると、現在の pull requests および今後のすべてのプル要求には `cla-signed` というラベルが付けられます。
