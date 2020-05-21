---
title: ローカルでの Git リポジトリの設定
description: この記事では、フォークや複製のプロセスなど、ローカル Git リポジトリの作成およびドキュメントへの投稿方法に関するガイダンスを示します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: jasonwhowell
ms.author: jasonh
ms.date: 01/18/2018
ms.openlocfilehash: e73c60c439285f901c5c83e538f8971d795bd6c4
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "72288594"
---
# <a name="set-up-git-repository-locally-for-documentation"></a>ドキュメントの Git リポジトリをローカルに設定する

この記事では、Microsoft のドキュメントに投稿することを目的として、ローカル コンピューターに git リポジトリを設定する手順について説明します。 共同作成者は、ローカルに複製されたリポジトリを使用して、新規記事の追加、既存の記事の大幅な編集、またはアートワークの変更を行うことができます。

投稿を開始するには、次の 1 回限りのセットアップ アクティビティを実行します。
> [!div class="checklist"]
> * 適切なリポジトリを決定する
> * GitHub アカウントにリポジトリをフォークする
> * 複製されたファイルのローカル フォルダーを選択する
> * ローカル コンピューターにリポジトリを複製する
> * アップストリームのリモート値を構成する

> [!IMPORTANT]
> 記事に軽微な変更しか加えていない場合は、この記事の手順を完了する必要*はありません*。 [簡易的な変更のワークフロー](index.md#quick-edits-to-existing-documents)に直接進むことができます。
>

## <a name="overview"></a>概要

Microsoft のドキュメント サイトに投稿するには、対応するドキュメント リポジトリを複製して、マークダウン ファイルをローカルで作成および編集します。 Microsoft では、GitHub アカウントに適切なリポジトリをフォークすることを要求しています。それにより、予定している変更を保存するための読み取り/書き込み権限が付与されます。 その後、pull requests を使用して、変更を読み取り専用の一元的な共有リポジトリにマージします。

![GitHub の三角形](./media/git-and-github-initial-setup.png)

GitHub を初めて使用する場合は、次のビデオを視聴して、フォークと複製のプロセスの概念について概要を確認します。

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>リポジトリを決定する

[docs.microsoft.com](https://docs.microsoft.com) にホストされているドキュメントは、[github.com](https://www.github.com) のいくつかの異なるリポジトリに存在します。

1. 使用するリポジトリが不明な場合は、Web ブラウザーを使用して [docs.microsoft.com](https://docs.microsoft.com) 上の記事にアクセスします。 記事の右上にある **[Edit]\(編集\)** リンク (鉛筆のアイコン) を選択します。

   ![[編集] をクリックしてリポジトリとファイルの場所を特定します。](media/index/edit-article.png)

2. このリンクでは、適切なリポジトリ内の対応するマークダウン ファイルがある github.com の場所に移動します。 リポジトリ名を表示するための URL にご注意ください。

   ![リポジトリの場所を特定する URL にご注意ください。](media/public-repo.png)

   たとえば、よく使用される次のリポジトリは公開投稿に使用できます。
   - Azure ドキュメント[https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - SQL Server ドキュメント[https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Visual Studio ドキュメント[https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - .NET ドキュメント[https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Azure .NET SDK ドキュメント[https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)
   - ConfigMgr ドキュメント [https://github.com/MicrosoftDocs/SCCMdocs](https://github.com/MicrosoftDocs/SCCMdocs/)

## <a name="fork-the-repository"></a>リポジトリのフォーク
適切なリポジトリを使用し、GitHub Web サイトで GitHub アカウントにリポジトリのフォークを作成します。

メインのドキュメント リポジトリはすべて読み取り専用アクセスを提供するため、個人のフォークが必須になります。 変更するには、自分のフォークからメイン リポジトリに[pull request](git-github-fundamentals.md#pull-requests)を送信する必要があります。 このプロセスを容易にするには、まずリポジトリの独自のコピーが必要になります。このコピーでは、書き込みアクセス権を持ちます。 GitHub の "*fork*" はその目的にかなっています。

1. メイン リポジトリの GitHub ページに移動して、右上の **[Fork]\(フォーク\)** ボタンをクリックします。

   ![GitHub プロファイルの例](./media/contribute-get-started-setup-local/fork.png)

2. メッセージが表示されたら、フォークの作成先として、GitHub アカウント タイルを選択します。 これにより、GitHub アカウント内にフォークと呼ばれるリポジトリのコピーが作成されます。

## <a name="choose-a-local-folder"></a>ローカル フォルダーを選択する
リポジトリのコピーをローカルで保持するためのローカル フォルダーを作成します。 一部のリポジトリは大きくなることがあります。たとえば、azure-docs は最大で 5 GB になります。 利用可能なディスク領域がある場所を選択します。

1. 覚えやすく入力しやすいフォルダー名を選択します。 たとえば、ルート フォルダー `C:\docs\` を使用するか、ユーザー プロファイル ディレクトリ `~/Documents/docs/` にフォルダーを作成することを検討してください

   > [!IMPORTANT]
   > 別の Git リポジトリ フォルダーの場所内に入れ子になっているローカル フォルダーの場所を選択しないてください。 相互に隣接された Git 複製フォルダーを格納することは可能ですが、相互の Git フォルダー内に Git フォルダーを入れ子にすると、ファイルの追跡でエラーが発生する原因になります。

2. Git Bash を起動します。

   ![Git Bash を起動します。](./media/contribute-get-started-setup-local/gitbash-start.png)

   Git Bash を起動する既定の場所は、Windows では一般的にホーム ディレクトリ (~) または `/c/users/<Windows-user-account>/` です。

   現在のディレクトリを確認するには、$ プロンプトで「`pwd`」と入力します。 

3. レポジトリをローカルでホストするために作成したフォルダー内にディレクトリを変更します (cd)。 Git Bash では、フォルダー パスにバックスラッシュの代わりに Linux 規則であるフォワード スラッシュを使用します。

   たとえば、`cd /c/docs/ ` や `cd ~/Documents/docs/` のようにします。

## <a name="create-a-local-clone"></a>ローカル複製を作成する

Git Bash を使用し、**clone** コマンドを実行してデバイスの現在のディレクトリにリポジトリのコピー (自分のフォーク) をプルすることを準備します。 

### <a name="authenticate-by-using-git-credential-manager"></a>Git Credential Manager を使用した認証
最新バージョンの Git for Windows をインストールして、既定のインストールを受け入れた場合、Git Credential Manager は既定で有効になります。 Git Credential Manager を使用すると、GitHub との認証済み接続およびリモートを再確立するときに、個人用アクセス トークンをあらためて呼び出す必要がなくなるため、認証が大幅に簡単になります。

1. リポジトリ名を指定して **clone** コマンドを実行します。 複製によって、フォークされたリポジトリがローカル コンピューターにダウンロード (複製) されます。 

    > [!Tip]
    > GitHub UI の **[Clone or download]\(複製またはダウンロード\)** から、clone コマンド用のフォークの GitHub URL を取得できます。
    >
    > ![[Clone or download]\(複製またはダウンロード\)](./media/contribute-get-started-setup-local/clone-or-download.png)

    複製処理中に、フォークの作成元のメイン リポジトリではなく、*フォーク*のパスを指定します。 そのようにしないと、変更に協力できません。 フォークは、個人用の GitHub ユーザー アカウント (`github.com/<github-username>/<repo>` など) を通じて参照されます。

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    clone コマンドは次の例のようになります。

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. メッセージが表示されたら、GitHub 資格情報を入力します。

    ![GitHub ログイン](./media/contribute-get-started-setup-local/github-login.png)

3. メッセージが表示されたら、2 要素認証コードを入力します。

    ![GitHub 2 要素認証](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > 資格情報は保存されて、今後の GitHub 要求の認証に使用されます。 コンピューターごとに 1 回だけこの認証を行う必要があります。 

4. clone コマンドを実行すると、リポジトリ ファイルのコピーをフォークからローカル ディスク上の新しいフォルダーにダウンロードします。 新しいフォルダーは現在のフォルダー内に作成されます。 リポジトリのサイズによっては数分かかることがあります。 処理が終了したらフォルダーを調べて構造を確認することができます。

## <a name="configure-remote-upstream"></a>リモート アップストリームを構成する
レポジトリを複製した後に、**upstream** という名前のメイン リポジトリへの読み取り専用のリモート接続をセットアップします。 upstream URL を使用して、他のユーザーが行った最新の変更と、ローカル リポジトリを常に同期しておくことができます。 **git remote** コマンドは、構成値を設定するために使用します。 **fetch** コマンドを使用して upstream リポジトリからブランチの情報を更新します。

1. **Git Credential Manager** を使用している場合は、次のコマンドを使用します。 \<repo\> および \<organization\> プレースホルダーを置き換えます。
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. 構成された値を表示し、URL が正しいことを確認します。 **origin** URL が個人用フォームを指していることを確認します。 **upstream** URL が MicrosoftDocs や Azure などのメイン リポジトリを指していることを確認します。 
   ```bash
   git remote -v 
   ```

   リモート出力の例を示します。 リポジトリ azure-docs にアクセスするための個人用アクセス トークンを使用して MyGitAccount という名前の架空の Git アカウントが構成されます。
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. 誤りがある場合は、リモート値を削除することができます。 upstream 値を削除するには、`git remote remove upstream` コマンドを実行します。

## <a name="next-steps"></a>次のステップ
- コンテンツの追加と更新の詳細については、[GitHub 共同作成ワークフロー](how-to-write-workflows-major.md)に関するページに進んでください。
