---
title: ドキュメントでのリンクの使用方法
description: この記事では、docs.microsoft.com 内でのコンテンツへのリンクの作成に関するガイドを提供します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: gewarren
ms.author: gewarren
ms.date: 10/31/2018
ms.openlocfilehash: 970f80b4e6ce795e0e2f15192d31680d7de6d35b
ms.sourcegitcommit: a812d716b31084926b886b93923f9b84c9b23429
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2019
ms.locfileid: "75188324"
---
# <a name="use-links-in-documentation"></a>ドキュメントでリンクを使用する

この記事では、docs.microsoft.com でホストされたページからハイパーリンクを使用する方法について説明します。 いくつかの規則が変更されていますが、リンクは Markdown に簡単に追加できます。 リンクは、同じページ内か、近くにある他のページ内か、外部のサイトや URL 上のコンテンツを指します。

docs.microsoft.com サイトのバックエンドでは、Open Publishing Services (OPS) が使われています。これは、[Markdig](https://github.com/lunet-io/markdig) 解析エンジンを使って解析される [CommonMark](https://commonmark.org/) 準拠のマークダウンをサポートしています。 ほとんどのドキュメントが GitHub に格納され、そこで編集可能であるように、このマークダウンのフレーバーのほとんどは [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) と互換性があります。 Markdown の拡張機能を通じて、その他の機能が追加されています。

> [!IMPORTANT]
> ターゲットでサポートされている場合 (このケースが大半) は必ず、すべてのリンクをセキュリティで保護する必要があります (`http` ではなく `https`)。

## <a name="link-text"></a>リンク テキスト

リンク テキストに含める単語はわかりやすくすることをお勧めします。 つまり、通常の英単語にするか、リンク先のページのタイトルにします。

> [!IMPORTANT]
> 「ここをクリック」は使用しないでください。 検索エンジンの最適化としては好ましくなく、リンク先の説明としても的確ではありません。

**正確:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**不正確:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>1 つの記事から別の記事へのリンク

同じ *docset* 内で 1 つの Docs 技術情報記事から別の Docs 技術情報記事へのインライン リンクを作成するには、次のリンク構文を使用します。

- 記事を同じディレクトリの別の記事にリンクする場合:

  `[link text](article-name.md)`

- 記事を現在のディレクトリの親ディレクトリにある記事にリンクする場合:

  `[link text](../article-name.md)`

- 記事を現在のディレクトリのサブディレクトリにある記事にリンクする場合:

  `[link text](directory/article-name.md)`

- 記事を現在のディレクトリの親ディレクトリのサブディレクトリにある記事にリンクする場合:

  `[link text](../directory/article-name.md)`

> [!NOTE]
> 前述の例で `~/` をリンクの一部としているものはありません。 リポジトリのルートから始まる絶対パスにリンクするには、リンクを `/` から始めます。 GitHub のソース リポジトリを移動するときに `~/` が生成する無効なリンクを含みます。 `/` が正しく解決するパスから始めます。

異なる docset 内の記事にリンクするには、そのファイルが同じリポジトリ内にある場合でも、次の構文を使用します。

`[link text](/docset-root/directory/article-name)`
   
たとえば、ルート URL が `https://docs.microsoft.com/dotnet` である記事を、ルート URL が `https://docs.microsoft.com/visualstudio` である記事にリンクする場合、リンクは `[link text](/visualstudio/directory/article-name)` のようになります。

> [!TIP]
> 同じ *docset* 内の記事は、"docs.microsoft.com" の後の URL フラグメントが同じになります。 たとえば、`https://docs.microsoft.com/dotnet/core/get-started` と `https://docs.microsoft.com/dotnet/framework/install` は同じ docset 内にあり、`https://docs.microsoft.com/dotnet/core/get-started` と `https://docs.microsoft.com/visualstudio/whats-new` は別々の docset 内にあります。

## <a name="links-to-anchors"></a>アンカーへのリンク

アンカーを作成する必要はありません。 アンカーは、公開時に、すべての H2 見出しについて自動的に生成されます。 唯一行う必要がある処理は、H2 セクションへのリンクを作成することです。

- 同じ記事内の見出しにリンクする場合

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- 別の記事のアンカーにリンクする場合:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>インクルードからのリンク

インクルード ファイルは別のディレクトリにあるため、より長い相対パスを使用する必要があります。 インクルード ファイルから記事にリンクするには、次のフォーマットを使用します。

   ```markdown
   [link text](../articles/folder/article-name.md)
   ```

## <a name="links-in-selectors"></a>セレクターのリンク

セレクターは、ドロップダウン リストとしてドキュメント記事に表示されるナビゲーション コンポーネントです。 閲覧者がドロップダウンの値を選択すると、選択した記事がブラウザーで開きます。 通常、セレクター リストには、関連性の高い記事のリンクが含まれます。たとえば、同じ題目が複数のプログラミング言語で提示されたり、関連性の高い一連の記事が提示されたりします。 

セレクターがインクルードに埋め込まれている場合、次のリンク構造を使用してください。

   ```markdown
   > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
   - [(Text1 | Example1 )](../articles/folder/article-name1.md)
   - [(Text1 | Example2 )](../articles/folder/article-name2.md)
   - [(Text2 | Example3 )](../articles/folder/article-name3.md)
   - [(Text2 | Example4 )](../articles/folder/article-name4.md) -->
   ```

## <a name="reference-style-links"></a>参照形式のリンク

参照形式のリンクを使用することで、ソース コンテンツをさらに読みやすくすることができます。 参照形式のリンクを使用すると、インライン リンク構文を、簡素化された構文で置き換えることができます。この構文によって、長い URL を記事の最後に移動することができます。 [Daring Fireball](https://daringfireball.net/projects/markdown/) の例を次に示します。

インライン テキスト:

   ```markdown
   I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].
   ```

記事の最後のリンク参照:

   ```markdown
   <!--Reference links in article-->
   [1]: http://google.com/
   [2]: http://search.yahoo.com/
   [3]: http://search.msn.com/
   ```
   
コロンの後、リンクの前に必ずスペースを入れます。 他の技術情報記事にリンクする際に、スペースを入れ忘れてしまった場合、リンクが破損した状態で記事が公開されます。

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>技術ドキュメント セットではないページへのリンク

別の Microsoft 資産のページ (価格のページ、SLA のページ、その他ドキュメントの記事ではないもの) にリンクする場合は、絶対 URL を使用しますが、ロケールは省略します。 ここでの目的は、リンクが GitHub と次に示すサイトで作動することです。

   ```markdown
   [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)
   ```
   
## <a name="links-to-third-party-sites"></a>サード パーティのサイトへのリンク

最高のユーザー体験は、別サイトへのユーザーの誘導を最小限に抑えます。 そのため、サード パーティのサイトにリンクする必要がある場合は、次の情報に基づいて行ってください。

- **アカウンタビリティ**:共有する情報がサード パーティの情報である場合に、サード パーティのコンテンツにリンクする。 たとえば、Microsoft のサイトで Android Developer Tools の使用方法の説明はしません。これは、Google が説明するべきことです。 必要であれば、Azure *で* Android 開発者用ツールを使用する方法を説明することはできますが、Google のツールの使用方法は、Google が説明することです。
- **PM サインオフ**:サード パーティのコンテンツに対して Microsoft サインオフを要求する。 サード パーティのコンテンツにリンクすることは、Microsoft がそのコンテンツを信頼していること、またユーザーがその指示に従った場合の Microsoft の責任を意味することになります
- **情報の鮮度のレビュー**:サード パーティの情報がまだ最新で、適切で、関連があり、リンクが変更されていないことを確認する。
- **オフサイト**:別のサイトに移動していることをユーザーが認識できるようにする。 それが明確でない状況の場合は、適切なフレーズを追加します。 次に例を示します。"必要条件に Android Developer Tools が含まれています。これは Android Studio サイトでダウンロードできます。"
- **次の手順**:「次の手順」セクションには、たとえば MVP のブログに対するリンクを追加しても構いません。 この場合も、サイトを離れることをユーザーが必ず認識できるようにしてください
- **法的情報**:Microsoft は、すべての ms.com ページにおいて、**利用条件**フッターの**サード パーティのサイトへのリンク**によって法的に保護されています。

## <a name="links-to-azure-powershell-reference-content"></a>Azure PowerShell 関連コンテンツへのリンク

Azure PowerShell 関連のコンテンツは、2016 年 11 月以来、数回の変更を重ねています。 docs.microsoft.com の他の記事からこのコンテンツにリンクする場合は、次のガイドラインを使用してください。

URL の構造:

* コマンドレットの場合:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* 概念についてのトピックの場合:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

`<moniker-name>` 部分は任意です。 省略した場合は、コンテンツの最新バージョンに移動します。 `<service-name>` 部分は次のベース URL に示す例のいずれかです。

- Azure PowerShell (AzureRM) のコンテンツ: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)
- Azure PowerShell (ASM) のコンテンツ: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)
- Azure Active Directory (AzureAD) PowerShell のコンテンツ: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)
- Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)
- Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)
- Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)

これらの URL を使用すると、コンテンツの最新バージョンにリダイレクトされます。 この方法を使うと、バージョン モニカーを指定する必要はありません。 また、バージョンが変わったときに更新する必要がある概念的コンテンツへのリンクも保持しません。

正確なリンクを作成するには、リンク先となるページをブラウザーで探し、その URL をコピーして、ロケール コード (たとえば、**en-us**) を削除します。

Markdown の例

```markdown
[Get-AzureRmResourceGroup](https://docs.microsoft.com/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](https://docs.microsoft.com/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](https://docs.microsoft.com/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](https://docs.microsoft.com/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps)
```
