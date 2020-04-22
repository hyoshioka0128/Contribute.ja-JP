---
title: Microsoft Docs 共同作成者ガイド概要
description: このガイドでは、Microsoft ドキュメント サイト docs.microsoft.com で共同作成を行う方法について説明します。
author: billwagner
ms.author: wiwagn
ms.date: 02/19/2019
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.openlocfilehash: 95dadff41bb31e0b34ee34f85ae47708297954f1
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81784276"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Microsoft Docs 共同作成者ガイド概要

[docs.microsoft.com](https://docs.microsoft.com) (Docs) 共同作成者ガイドへようこそ。

Microsoft のドキュメント セットには、オープン ソースで GitHub 上でホストされているのものがいくつかあります。 すべてのドキュメント セットが完全にオープン ソースであるわけではありませんが、多くには一般公開用のリポジトリが備わっていて、そこで pull request を使って提案された変更を加えることができます。 このようなオープン ソースのアプローチにより、製品エンジニア、コンテンツ チーム、およびお客様との間のコミュニケーションが合理化され、改善されます。また、その他の利点があります。

- オープン ソースのリポジトリにより "_一般公開された状態で計画を行う_" ことで、最も必要とされているドキュメントがどれであるかについてのフィードバックを得る。
- オープン ソースのリポジトリにより "_一般公開された状態でレビューを行う_" ことで、最も役に立つコンテンツを最初のリリースで公開する。
- オープン ソースのリポジトリにより "_一般公開された状態で更新を行う_" ことで、コンテンツの継続的な改善を容易にする。

[docs.microsoft.com](https://docs.microsoft.com) のユーザー エクスペリエンスには [GitHub](https://github.com) のワークフローが直接統合され、さらに簡単になっています。 まずは[表示しているドキュメントを編集](#quick-edits-to-existing-documents)してみましょう。 または、[新しいトピックをレビュー](#review-open-prs)して支援するか、[品質に関するイシューを作成します](#create-quality-issues)。

> [!IMPORTANT]
> docs.microsoft.com に公開されるすべてのリポジトリには、「[Microsoft Open Source Code of Conduct (Microsoft オープン ソース倫理規定)](https://opensource.microsoft.com/codeofconduct/)」または「[.NET Foundation Code of Conduct (.NET Foundation 倫理規定)](https://dotnetfoundation.org/code-of-conduct)」が適用されています。 詳細については、[倫理規定に関する FAQ](https://opensource.microsoft.com/codeofconduct/faq/) のページを参照してください。 または、ご質問やコメントがある場合は、[opencode@microsoft.com](mailto:opencode@microsoft.com) または [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) までご連絡ください。<br>
>
> パブリック リポジトリにあるドキュメントおよびコード例に対する軽微な修正や明確化は、「[docs.microsoft.com - 使用条件](https://docs.microsoft.com/legal/termsofuse)」の対象になります。 お客様が Microsoft の従業員ではない場合、新規または大幅な変更を加えると、オンラインの貢献者使用許諾契約書 (CLA) のご提出をお願いするコメントが pull request 内に生成されます。 このオンライン フォームにご入力いただいてから、お客様の pull request に対するレビューや承認を実施いたします。

## <a name="quick-edits-to-existing-documents"></a>既存のドキュメントに対するクイック編集

クイック編集により、ドキュメント内の小さなエラーや漏れを報告および修正するプロセスが合理化されます。 さまざまな努力を重ねても、公開されたドキュメントには文法やスペルに関する小さな誤りが "_必ず_" 入り込みます。 イシューを作成して間違いを報告することもできますが、利用可能な場合は、pull request (PR) を作成して問題を修正するオプションの方が速くて簡単です。

1. 一部のドキュメント ページでは、ブラウザー内でコンテンツを直接編集できます。 その場合、以下に示すような **[編集]** ボタンが表示されます。 **[編集]** (または同等にローカライズされた) ボタンをクリックすると、GitHub 上のソース ファイルに移動します。 **[編集]** ボタン (テキストなしの鉛筆アイコン) がない場合は、そのドキュメント ページを変更することはできません。

   ![[編集] リンクの場所](./media/index/edit-article.png)

2. 次に、鉛筆アイコンをクリックして、以下のように記事を編集します。 鉛筆アイコンが灰色表示されている場合は、自分の GitHub アカウントにログインするか、新しいアカウントを作成する必要があります。 

   ![鉛筆アイコンの場所](./media/index/edit-icon.png)


3. Web エディターで変更を加えます。 **[変更のプレビュー]** タブをクリックして、自分の変更の書式設定を確認します。

4. 変更を加えたら、ページの一番下までスクロールします。 次の図に示すように、自分の変更にタイトルと説明を入力して、 **[Propose file change]\(ファイル変更の提案\)** をクリックします。

   ![ファイル変更の提案](./media/index/submit-pull-request.png)

5. 変更の提案が済みましたので、その変更をリポジトリに "pull" するよう、そのリポジトリの所有者に依頼する必要があります。 これを完了するには、"pull request" と呼ばれる作業を実行します。 上の図の **[Propose file change ]\(ファイル変更の提案\)** をクリックした場合、次の図のような新しいページに移動しているはずです。

   ![pull request の作成](media/index/create-pull-request.png)

   **[Create pull request]\(pull request の作成)** をクリックし、pull request のタイトル (および必要に応じて説明) を入力した後、もう一度 **[Create pull request]\(pull request の作成)** をクリックします。 (GitHub を初めてお使いの場合、詳細については「[About Pull Requests (pull request について)](https://help.github.com/en/articles/about-pull-requests)」を参照してください。)

6. これで終了です。 コンテンツ チームのメンバーが、お客様の PR をレビューしてマージします。 大規模な変更を加えた場合、変更をお願いするフィードバックを受け取る可能性があります。

GitHub の編集用 UI は、リポジトリに対する自分のアクセス許可に対応しています。 上の図のとおりになるのは、対象のリポジトリに対する書き込みアクセス許可がない共同作成者の場合です。 GitHub により、対象のリポジトリのフォークが自分のアカウント内に自動的に作成されます。 対象のリポジトリへの書き込みアクセス権がある場合は、GitHub により対象のリポジトリに新しいブランチが作成されます。 ブランチ名は **\<GitHubId\>-patch-n** という形式になり、ご自身の GitHub ID と、パッチのブランチ用の数値識別子が使われます。

書き込みアクセス権がある共同作成者の場合も、すべての変更に対して pull request が使われます。 更新が必ず pull request として提出されるように、ほとんどのリポジトリでは `master` ブランチが保護されています。

ブラウザー内の編集操作は、軽微または頻度の低い変更を行う場合に最適です。 大規模な共同作成を行う場合、または Git の高度な機能 (ブランチ管理や高度なマージ競合の解決など) を使用する場合は、[リポジトリをフォークしてローカルで作業する](how-to-write-workflows-major.md)必要があります。

> [!NOTE]
> 有効な場合、**任意の言語**で記事を編集できます。また、編集の種類に基づいて、次のことが起こります。
> 1. 承認された言語的な変更は、Microsoft の機械翻訳エンジンの改善にも役立てられます
> 2. 編集によって記事のコンテンツが大幅に変更された場合、内部的に処理され、同じ記事の英語版に変更が送信されます。承認された場合はすべての言語でローカライズされます。
> ご提案いただいた改善は、ご自身の言語だけでなく、利用可能なすべての言語の記事に良い影響を与えます。

## <a name="review-open-prs"></a>オープン中の PR をレビューする

現在オープン中の PR を確認することで、新しいトピックを公開前に読むことができます。 レビューは [GitHub フロー](https://guides.github.com/introduction/flow/)のプロセスに従います。 提案された更新内容や新しい記事をパブリック リポジトリ内で閲覧できます。 それらをレビューしてコメントを追加します。 任意のドキュメント リポジトリをご覧いただき、関心のある領域について、オープン中の pull requests (PR) をご確認くださ。 提案された更新内容に対するコミュニティのフィードバックは、コミュニティ全体の役に立ちます。

## <a name="create-quality-issues"></a>品質に関するイシューを作成する

Microsoft のドキュメントは、進行中の継続的な作業です。 適切なイシューは、コミュニティの最優先事項に注力するために役立ちます。 提供していただく情報が詳細なほど、イシューは役立つものになります。 お探しだった情報を教えてください。 ご使用になった検索語句を教えてください。 初めてお使いいただくテクノロジについてどう使い始めたらよいのかが不明瞭だった場合、どのようにするのが望ましいかをお聞かせください。

Microsoft のドキュメント ページの多くには、ページの下部に「**フィードバック**」セクションがあります。これをクリックして**製品のフィードバック**または**コンテンツに関するフィードバック**を入力し、その記事に固有のイシューを追跡することができます。

イシューによって、何が必要とされているかについての会話が開始されます。 コンテンツ チームでは、追加できる内容のご提案を含めてこのようなイシューに回答し、ご意見を伺います。 ドラフトを作成し次第、お客様に [PR のレビュー](#review-open-prs)を依頼いたします。

## <a name="get-more-involved"></a>さらに深く関わる

その他のトピックは、Microsoft Docs に対する共同作成を生産的に開始するのに役立ちます。これらでは、Microsoft Docs プラットフォームで使用される GitHub リポジトリ、Markdown ツール、および拡張機能の操作について説明しています。
