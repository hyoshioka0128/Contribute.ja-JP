---
title: ドキュメントでのリンクの使用方法
description: この記事では、docs.microsoft.com 内でのコンテンツへのリンクの作成に関するガイドを提供します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: gewarren
ms.author: gewarren
ms.date: 03/31/2020
ms.openlocfilehash: ca29d4b9e81f8af3b680367b210bd1734860687d
ms.sourcegitcommit: 5ef2dc72e2ff8bddf873415a3f4b816eb16029dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80624800"
---
# <a name="use-links-in-documentation"></a>ドキュメントでリンクを使用する

この記事では、docs.microsoft.com でホストされたページからハイパーリンクを使用する方法について説明します。 いくつかの規則が変更されていますが、リンクは Markdown に簡単に追加できます。 リンクは、同じページ内か、近くにある他のページ内か、外部のサイトや URL 上のコンテンツを指します。

docs.microsoft.com サイトのバックエンドでは、Open Publishing Services (OPS) が使われています。これは、[Markdig][] 解析エンジンを使って解析される [CommonMark][] 準拠のマークダウンをサポートしています。 ほとんどのドキュメントが GitHub に格納され、そこで編集可能であるように、このマークダウンのフレーバーのほとんどは [GitHub Flavored Markdown (GFM)][GFM] と互換性があります。 Markdown の拡張機能を通じて、その他の機能が追加されています。

> [!IMPORTANT]
> ターゲットでサポートされている場合 (このケースが大半) は必ず、すべてのリンクをセキュリティで保護する必要があります (`http` ではなく `https`)。

## <a name="link-text"></a>リンク テキスト

リンク テキストに含める単語はわかりやすくすることをお勧めします。 つまり、通常の英単語にするか、リンク先のページのタイトルにします。

> [!IMPORTANT]
> 「ここをクリック」は使用しないでください。 検索エンジンの最適化としては好ましくなく、リンク先の説明としても的確ではありません。

**正確:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://docs.microsoft.com/sql/t-sql/statements/set-transaction-isolation-level-transact-sql) reference.`

**不正確:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>1 つの記事から別の記事へのリンク

公開システムでサポートされるハイパーリンクには、**URL** と**ファイル リンク**の 2 種類があります。

URL リンクは、docs.microsoft.com のルートに対して相対的な URL パス、または完全な URL 構文を含む絶対 URL (たとえば、`https://github.com/MicrosoftDocs/PowerShell-Docs`) のいずれかです。

- 現在の _docset_ 以外のフォルダーにあるコンテンツにリンクする場合、または docset 内の自動生成されたリファレンスおよび概念説明の記事の間でリンクする場合は、URL リンクを使用します。
- 相対リンクを作成する最も簡単な方法は、ブラウザーから URL をコピーし、マークダウンに貼り付けた値から `https://docs.microsoft.com/en-us` を削除することです。
   - Microsoft のプロパティの URL にロケールを含めないでください (たとえば、URL から "/en-us" を削除してください)。

ファイル リンクは、docset 内のある記事から別の記事にリンクするために使用します。

- すべてのファイル パスで、バックスラッシュ文字ではなくスラッシュ (`/`) 文字を使用します。
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

### <a name="structure-of-links-on-docsmicrosoftcom"></a>docs.microsoft.com 上のリンク構造

docs.microsoft.com で公開されるコンテンツの URL 構造は、次のとおりです。

```
https://docs.microsoft.com/<locale>/<product-service>/[<feature-service>]/[<subfolder>]/<topic>[?view=<view-name>]
```

例:

```
https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-overview
https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-5.1.1
```

- `<locale>` - 記事の言語を識別します (例: en-us、de-de)
- `<product-service>` - 製品またはサービスの名前 (例: powershell、dotnet、azure)
- `[<feature-service>]` - (省略可能) 製品の機能またはサブサービスの名前 (例: csharp、load-balancer)
- `[<subfolder>]` - (省略可能) 機能内のサブフォルダーの名前
- `<topic>` - トピックの記事ファイルの名前 (例: load-balancer-overview、overview)
- `[?view=\<view-name>]` - (省略可能) 複数のバージョンが使用可能なコンテンツのバージョン セレクターで使用されるビュー名 (例: azps-3.5.0)

> [!TIP]
> ほとんどの場合、同じ _docset_ 内の記事は、`<product-service>` URL フラグメントが同じになります。 次に例を示します。
> - 同じ docset
>   - `https://docs.microsoft.com/dotnet/core/get-started`
>   - `https://docs.microsoft.com/dotnet/framework/install`
> - 異なる docset
>   - `https://docs.microsoft.com/dotnet/core/get-started`
>   - `https://docs.microsoft.com/visualstudio/whats-new`

## <a name="bookmark-links"></a>ブックマーク リンク

"*現在の*" ファイル内にある見出しへのブックマーク リンクについては、ハッシュ記号を使用し、その後に見出しの語を小文字で続けます。 見出しから句読点を削除し、スペースをダッシュに置き換えます。

```markdown
[Managed Disks](#managed-disks)
```

別の記事にあるブックマーク見出しにリンクするには、ファイル相対リンクまたはサイト相対リンクに加えてハッシュ記号を使用し、その後に見出しの語を続けます。 見出しから句読点を削除し、スペースをダッシュに置き換えます。

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

また、URL からブックマーク リンクをコピーすることもできます。 URL を見つけるには、docs.microsoft.com の見出し行の上にマウスを位置付けます。 リンク アイコンが表示されます。

![記事の見出しに表示されたリンク アイコン](media/how-to-write-links/bookmark-link.png)

リンク アイコンをクリックして、URL からブックマークのアンカー テキストをコピーします。

> [!NOTE]
> Docs 拡張機能には、リンクの作成に役立つツールも用意されています。

### <a name="explicit-anchor-links"></a>明示的なアンカー リンク

ハブ ページとランディング ページを除いて、`<a>` HTML タグを使用して明示的なアンカー リンクを追加する必要はなく、推奨されません。 代わりに、「[ブックマーク リンク](#bookmark-links)」の説明に従って、自動生成されたブックマークを使用します。 ハブ ページとランディング ページについては、アンカーを次のように宣言します。

```markdown
## <a id="anchortext" />Header text
```

または

```markdown
## <a name="anchortext" />Header text
```

アンカーへのリンクは次のようになります。

```markdown
To go to a section on the same page:
[text](#anchortext)

To go to a section on another page.
[text](filename.md#anchortext)
```

> [!NOTE]
> アンカー テキストは必ず小文字で、スペースは使用できません。

## <a name="xref-cross-reference-links"></a>XRef (相互参照) リンク

XRef リンクはビルド時に検証されるため、API へのリンクには、このリンクを使用することをお勧めします。 現在の docset または他の docset 内の自動生成された API リファレンス ページにリンクするには、種類またはメンバーの一意な ID ([UID](#determine-the-uid)) を含む XRef リンクを使用します。

> [!TIP]
> [.NET API ブラウザー][]に表示される .NET XRref リンクを挿入するには、[VS Code 用の Docs Markdown 拡張機能][docsextension] (Docs Authoring Pack の一部) を使用します。

リンク先の API が [docs.microsoft.com][docs] 上にあるかどうかを確認します。このためには、[.NET API ブラウザー][]または [Windows UWP][] 検索ボックスに、完全な名前の全部または一部を入力します。 結果が何も表示されない場合、その型はまだ docs.microsoft.com 上にありません。

次のいずれかの構文を使用できます。

- 自動リンク:

   ```markdown
   <xref:UID>
   <xref:UID?displayProperty=nameWithType>
   ```

   既定では、リンク テキストに表示されるのはメンバー名または型名のみです。 オプションの `displayProperty=nameWithType` クエリ パラメーターは、完全修飾されたリンク テキストを生成します。つまり、型の場合は **namespace.type**、列挙型メンバーを含む型メンバーの場合は **type.member** になります。

- Markdown スタイルのリンク:

   ```markdown
   [link text](xref:UID)
   ```

   表示されるリンク テキストをカスタマイズする場合は、Markdown スタイルの XRef リンクを使用します。

例:

- **\<xref:System.String>** は、<xref:System.String> として表示されます。

- **\<xref:System.String?displayProperty=nameWithType>** は、<xref:System.String?displayProperty=nameWithType> として表示されます。

- **\[String class](xref:System.String)** は、[String クラス](xref:System.String)として表示されます。

`displayProperty=fullName` クエリ パラメーターは、クラスの `displayProperty=nameWithType` と同様に動作します。 つまり、リンク テキストは、**namespace.classname** になります。 ただし、メンバーの場合は、リンク テキストは、**namespace.classname.membername** として表示されます。これは、望ましくない可能性があります。

> [!NOTE]
> UID は、大文字と小文字が区別されます。 たとえば、`<xref:System.Object>` は正しく解決されますが、`<xref:system.object>` は正しく解決されません。

### <a name="xref-build-warnings-and-incremental-builds"></a>XRef ビルド警告とインクリメンタル ビルド

インクリメンタル ビルドでは、変更されたファイル、または変更の影響を受けたファイルのみがビルドされます。 無効な XRef リンクに関するビルド警告が表示されても、そのリンクが実際は有効な場合、ビルドがインクリメンタル ビルドである可能性があります。 警告の原因となったファイルが変更されていないため、そのファイルはビルドされず、過去の警告が再度表示されました。 ファイルが変更されるか、完全なビルドをトリガーすると (ops.microsoft.com で完全なビルドを開始できる場合)、警告は表示されなくなります。 DocFX は Xref サービス内のデータ更新を検出できないため、これはインクリメンタル ビルドの欠点です。

### <a name="determine-the-uid"></a>UID を決定する

通常、UID は、完全修飾されたクラスまたはメンバーの名前です。 UID を決定するには、少なくとも次の 2 つの方法があります。

- 型またはメンバーの [Docs][docs] ページで右クリックして、 **[ソースの表示]** を選択し、**ms.assetid** の **content** の値をコピーします。

  ![Web ページのソース内の ms.assetid](media/how-to-write-links/ms-assetid.png)

- 型の名前の一部または全部を URL に追加して、[オートコンプリート サイト][]を利用します。 たとえば、ブラウザーのアドレス バーに `https://xref.docs.microsoft.com/autocomplete?text=Writeline` と入力すると、名前に **Writeline** を含むすべての型とメソッドが、その UID とともに表示されます。

#### <a name="verify-the-uid"></a>UID を確認する

UID が正しいかどうかをテストするには、次の URL の **System.String**を自分の UID に置き換えて、それをブラウザーのアドレス バーに貼り付けます。

`https://xref.docs.microsoft.com/query?uid=System.String`

> [!TIP]
> URL 内の UID は、大文字と小文字が区別されます。メソッド オーバーロード URL を確認する場合、パラメーター型の間にスペースを入れないようにしてください。

次のような内容が表示された場合、正しい UID です。

```text
[{"uid":"System.String","name":"String","fullName":"System.String","href":"https://docs.microsoft.com/dotnet/api/system.string","tags":",/dotnet,netframework-4.5.1,netframework-4.5.2,netframework-4.5,...xamarinmac-3.0,public,","vendor":null,"hash":null,"commentId":"T:System.String","nameWithType":"System.String"},{"uid":"System.String","name":"String","fullName":"System.String","href":"https://docs.microsoft.com/dotnet/api/system.string","tags":",/dotnet,netframework-4.5.1,netframework-4.5.2,netframework-4.5,netframework-4.6,netframework-4.6.1,...,xamarinmac-3.0,public,","vendor":null,"hash":null,"commentId":"T:System.String","nameWithType":"System.String"}]
```

ページに `[]` だけが表示される場合、UID は正しくありません。

### <a name="percent-encoding-of-urls"></a>URL のパーセント エンコード

UID 内の特殊文字は、次のように HTML エンコードする必要があります。

| 文字 | HTML エンコード |
| --------- | ------------- |
| `` ` ``   | %60           |
| `#`       | %23           |
| `*`       | %2A           |

[パーセント エンコード](https://en.wikipedia.org/wiki/Percent-encoding)の完全な一覧を参照してください。

エンコード例:

- `System.Threading.Tasks.Task``1` は、`System.Threading.Tasks.Task%601` としてエンコードされます ([ジェネリック型に関するセクション](#generic-types)を参照してください)

- `System.Exception.#ctor` は、`System.Exception.%23ctor` としてエンコードされます

- `System.Object.Equals*` は、`System.Object.Equals%2A` としてエンコードされます

### <a name="generic-types"></a>ジェネリック型

ジェネリック型は、`System.Collections.Generic.List<T>` などの型です。 [.NET API ブラウザー](https://docs.microsoft.com/dotnet/api/)でこの型を参照し、その URL を調べると、`<T>` は、URL で `-1` として記述されていることがわかります。これは、実際には、 **`1** を表します。

`https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1`

**List\<T>** などのジェネリック型にリンクするには、次の例に示すように、 **\`** バックティック文字を **%60** としてエンコードします。

```markdown
<xref:System.Collections.Generic.List%601>
```

### <a name="methods"></a>メソッド

メソッドにリンクするには、メソッド名の後にアスタリスク (`*`) を追加してメソッドの全般ページにリンクするか、特定のオーバーロードにリンクします。 たとえば、特定のパラメーター型を指定しないで `<xref:System.Object.Equals%2A?displayProperty=nameWithType>` メソッドにリンクする場合に全般ページを使用します。 アスタリスク文字は、`%2A` としてエンコードされます。 次に例を示します。

<xref:System.Object.Equals%2A?displayProperty=nameWithType> への `<xref:System.Object.Equals%2a?displayProperty=nameWithType>` リンク

特定のオーバーロードにリンクするには、メソッド名の後にかっこを追加し、各パラメーターの完全な型名を含めます。 型名の間に空白文字を挿入しないでください。そうしなければ、リンクは機能しません。 次に例を示します。

<xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType>への `<xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType>` リンク

## <a name="links-from-includes"></a>インクルードからのリンク

インクルード ファイルは別のディレクトリにあるため、より長い相対パスを使用する必要があります。 インクルード ファイルから記事にリンクするには、次のフォーマットを使用します。

```markdown
[link text](../articles/folder/article-name.md)
```

> [!TIP]
> Visual Studio Code 用の [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) 拡張機能は、パスを確認するという面倒な作業を行わずに、相対リンクやブックマークを挿入するのに役立ちます。

## <a name="links-in-selectors"></a>セレクターのリンク

セレクターは、ドロップダウン リストとしてドキュメント記事に表示されるナビゲーション コンポーネントです。 閲覧者がドロップダウンの値を選択すると、選択した記事がブラウザーで開きます。 通常、セレクター リストには、関連性の高い記事のリンクが含まれます。たとえば、同じ題目が複数のプログラミング言語で提示されたり、関連性の高い一連の記事が提示されたりします。

セレクターがインクルードに埋め込まれている場合、次のリンク構造を使用してください。

   ```markdown
   > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
   - [(Text1 | Example1 )](../articles/folder/article-name1.md)
   - [(Text1 | Example2 )](../articles/folder/article-name2.md)
   - [(Text2 | Example3 )](../articles/folder/article-name3.md)
   - [(Text2 | Example4 )](../articles/folder/article-name4.md)
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
- **情報の鮮度のレビュー**:サードパーティの情報がまだ最新かつ正確であり、関連性があること、またリンクが変更されていないことを確認する。
- **オフサイト**:別のサイトに移動していることをユーザーが認識できるようにする。 それが明確でない状況の場合は、適切なフレーズを追加します。 次に例を示します。"前提条件に Android Developer Tools が含まれています。これは Android Studio サイトでダウンロードできます。"
- **次の手順**:"次の手順" セクションに、たとえば MVP のブログへのリンクを追加しても問題ありません。 この場合も必ず、サイトを離れることをユーザーが認識できるようにしてください。
- **法的情報**:Microsoft は、すべての microsoft.com ページで、**使用条件**フッターの「**第三者サイトへのリンク**」に法的な情報を明記しています。

<!-- link references -->
[CommonMark]: https://commonmark.org/
[Markdig]: https://github.com/lunet-io/markdig
[GFM]: https://help.github.com/categories/writing-on-github/
[docs]: https://docs.microsoft.com
[.NET API ブラウザー]: https://docs.microsoft.com/dotnet/api/
[Windows UWP]: https://docs.microsoft.com/uwp/api
[docsextension]: https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown
[オートコンプリート サイト]: https://xref.docs.microsoft.com/autocomplete?text=
