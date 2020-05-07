---
title: Git および GitHub のドキュメントの基礎
description: この記事では、Git、GitHub リポジトリの概要、コンテンツの編成、docs.microsoft.com で使用される命名規則について説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 06/30/2017
ms.openlocfilehash: c099a458718ade11840c314542c530dd6669402d
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "78331885"
---
# <a name="git-and-github-essentials-for-docs"></a>Git および GitHub のドキュメントの基礎

## <a name="overview"></a>概要

Docs コンテンツの共同作成者は、複数のツールやプロセスを操作します。 同じプロジェクトで他の共同作成者と並行して作業を行います。まったく同じコンテンツで同時に作業を行う場合もあります。 これらのすべては Git と GitHub ソフトウェアによって実現します。

Git はオープン ソースのバージョン管理システムです。 *リポジトリ* に存在するファイルの*分散型バージョン管理* により、この種のプロジェクト コラボレーションを容易にします。 要するに、Git を利用することで、特定のリポジトリを対象に複数の共同作成者によって長期間にわたって行われる一連の作業を統合できます。

GitHub は、[docs.microsoft.com](https://docs.microsoft.com) コンテンツの格納に使用しているような Git リポジトリの、Web ベースのホスティング サービスです。 GitHub は任意のプロジェクトのメイン リポジトリをホストします。共同作成者はこのメイン リポジトリから独自の作業用のコピーを作成できます 

## <a name="git"></a>Git

集中型バージョン管理システム (Team Foundation Server、SharePoint、Visual SourceSafe など) を使い慣れている場合、Git に分散型モデルをサポートする固有の共同作成ワークフローと用語があることに気付かれるでしょう。 たとえば、通常はチェックアウト/チェックイン操作と関連するファイル ロックはありません。 実際のところ、Git では最小レベルの変更でさえも考慮されており、ファイルはバイト単位で比較されます。

また、Git では階層化された構造を使用して、プロジェクトのコンテンツを格納および管理します。

- "*リポジトリ*" :*repo* とも呼ばれます。これはストレージの最上位の単位です。 リポジトリには 1 つまたは複数のブランチが含まれます。
- "*ブランチ*" :プロジェクトのコンテンツ セットを構成するファイルやフォルダーを含むストレージの単位です。 ブランチは作業ストリームを分離します (通常はバージョンと呼ばれる)。 共同作成の範囲は必ず特定のブランチに設定されます。 すべてのリポジトリには、既定のブランチ (通常の名前は "マスター") と、マスター ブランチにマージされることになるブランチが 1 つまたは複数含まれます。 マスター ブランチは、プロジェクトの現在のバージョンおよび "信頼できる唯一の情報源" となります。 これは、そのリポジトリ内の他のすべてのブランチの作成元となる親です。

共同作成者は以下の方法で Git と対話して、ローカル レベルと GitHub レベルの両方でリポジトリを更新および処理します。

- ローカルでは、ローカル リポジトリの管理や GitHub リポジトリとの通信のための Git のコマンドをサポートするツール (Git Bash コンソールなど) を利用します。
- Git を統合する [www.github.com](https://www.github.com) を利用して、メイン リポジトリに戻される共同作成の整合を管理します。

## <a name="github"></a>GitHub

> [!NOTE]
> Docs のガイダンスは GitHub の使用を前提としていますが、チームによっては Visual Studio Team Services を利用して Git リポジトリをホスティングします。 Visual Studio Team Explorer クライアントでは、コマンド ラインで Git コマンドを使用する代わりに、GUI を利用して Team Services リポジトリと対話できます。
> </br>
> また、後述のガイドラインの多くは、GitHub で Azure サービスのコンテンツをホストしてきた長年の経験からのベスト プラクティスとして開発されました。 一部の Docs リポジトリでは必須である可能性があります。

すべてのワークフローは任意の Docs プロジェクトのメイン リポジトリが格納されている GitHub レベルで始まり、GitHub レベルで終わります。 共同作成者が自分で使用するために作成するコピーは、複数のコンピューターに配信されます。 これらのコピーは最終的に、プロジェクトのメイン GitHub リポジトリに戻されて整合されます。

### <a name="directory-organization"></a>ディレクトリの構成

前述のとおり、プロジェクトの既定/マスター ブランチは、プロジェクト コンテンツの最新バージョンとして機能します。 マスター ブランチ (およびマスター ブランチから作成されたブランチ) のコンテンツは、対応する Docs ページの記事の組織と大まかに一致します。 お気に入りコンテンツ (サービスなど)、メディア コンテンツ (イメージ ファイルなど)、および "インクルード" ファイル (コンテンツの再利用を可能にする) を分離するために、サブディレクトリが使用されます。

通常、メイン `articles` ディレクトリはリポジトリのルートの直下にあります。 記事のディレクトリには一連のサブディレクトリが含まれます。 サブディレクトリ内の記事は、 *.md* 拡張子を使用する Markdown ファイルとして書式設定されます。 複数のサービスをサポートするリポジトリでは、共通の `/articles` サブディレクトリが使用されることがあります。たとえば、[Azure-Docs](https://github.com/MicrosoftDocs/Azure-Docs) リポジトリです。 サービス固有の名前が使用される場合もあります。たとえば、[IntuneDocs](https://github.com/MicrosoftDocs/IntuneDocs) リポジトリでは `/IntuneDocs` が使用されます。

このディレクトリのルートには、サービスまたは製品全体に関する記事全般があります。 通常ではその他に、機能/サービスまたは共通のシナリオに対応する一連のサブディレクトリがあります。 たとえば、Azure の "仮想マシン" に関する記事はサブディレクトリ `/virtual-machines` にあり、Intune の "理解と探索" に関する記事はサブディレクトリ `/understand-explore` にあります。

### <a name="media-subdirectory"></a>メディアのサブディレクトリ

各記事のディレクトリには、対応するメディア ファイルの `/media` サブディレクトリが含まれます。 メディア ファイルには、イメージ参照がある記事で使用されるイメージが含まれます。

### <a name="includes-subdirectory"></a>インクルード サブディレクトリ

2 つ以上の記事で共有される再利用可能なコンテンツがある場合は常に、メイン `articles` ディレクトリの直下にあるサブディレクトリ `/includes` に配置されます。 インクルード ファイルを使用する Markdown ファイルでは、インクルード ファイルが参照される必要がある場所に、対応する "include" Markdown の拡張機能が配置されます。

[Markdown リファレンスのインクルード](markdown-reference.md#included-markdown-files)に関するページにその他のガイダンスがあります。

### <a name="markdown-file-template"></a>Markdown ファイルのテンプレート

便宜上、各リポジトリのルート ディレクトリには通常、`template.md` という名前の Markdown テンプレート ファイルが含まれます。 新しい記事を作成してリポジトリに送信する必要がある場合は、このテンプレート ファイルを "開始ファイル" として使用できます。 ファイルには、次のものが含まれます。

- ファイルの冒頭にある**メタデータ ヘッダー**。3 つのハイフンで構成される 2 本の線で区切られます。 記事に関連する情報の追跡に使用される各種タグが含まれます。 記事のメタデータでは、作成者の属性、共同作成者の属性、階層リンク、および記事の説明など、特定の機能を使用できます。 これには、Microsoft がコンテンツのパフォーマンス評価に使用する SEO の最適化やレポート プロセスも含まれます。 したがって、メタデータは重要です。
- メタデータのさまざまなタグや値を説明する**メタデータ セクション**。 メタデータ セクションで使用する値がわからない場合、空白のままにするか、先頭にハッシュタグ (#) を付けたコメントを残すことができます。これらはリポジトリの pull request レビュー担当者によってレビュー/完了されます。
- 記事の要素の書式を設定するさまざまな **Markdown の使用例**。
- **Markdown 拡張機能の使用に関する説明**全般。これはさまざまな種類のアラートに使用できます。
- iframe を使用した**ビデオ埋め込み**の例。
- **docs.microsoft.com 拡張機能の使用に関する説明**全般。これはボタンやセレクターなどの特殊なコントロールに使用できます。

## <a name="pull-requests"></a>Pull request

*pull request* は、共同作成者が既定のブランチに適用される一連の変更内容を提案できる便利な手段です。 変更内容 (*コミット* ともいう) は共同作成者のブランチに格納されるため、GitHub は既定のブランチに変更内容を*マージする* 影響をあらかじめモデル化することができます。 Pull request は、変更内容が既定のブランチにマージされる前に潜在的な問題や疑問を解消するために、ビルド/検証プロセスや pull request のレビュー担当者からのフィードバックを共同作成者に提供するメカニズムとしても機能します。

提案する変更内容のサイズに応じて、pull request で共同作成を行う方法が 2 つあります。 これについては、このガイドで後述する [GitHub のワークフロー](how-to-write-workflows-major.md)に関するセクションで詳しく説明します。

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
