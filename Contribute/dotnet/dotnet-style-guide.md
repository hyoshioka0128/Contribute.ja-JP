---
title: .NET 記事のテンプレートとチートシート
description: この記事には、.NET ドキュメント リポジトリ用の新しい記事を作成するときに使用できる便利なテンプレートが含まれています
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 11/07/2018
ms.openlocfilehash: a520112cd77f4c4807e7719c2c4dbd43a762f062
ms.sourcegitcommit: bf2f4c7d9050b480d4db306df19d4c9f8714eff0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80759551"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a>.NET ドキュメントのメタデータと Markdown テンプレート

この dotnet/docs テンプレートには、Markdown 構文の例とメタデータの設定方法が含まれています。

Markdown ファイルを作成するとき、付属のテンプレートを新しいファイルにコピーし、下のようにメタデータに入力し、上の H1 見出しを記事のタイトルに設定してください。

## <a name="metadata"></a>メタデータ

必須のメタデータ ブロックは次のサンプル メタデータ ブロックにあります。

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- コロン (:) とメタデータ要素の値の間にはスペースを入れる**必要があります**。
- 値 (タイトルなど) 内のコロンによってメタデータ パーサーが中断されます。 その場合、タイトルを二重引用符で囲みます (例: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`)。
- **title**: 検索エンジンの結果に表示されます。 タイトルは H1 見出しのタイトルと同じにしないでください。また、60 文字以下にする必要があります。
- **説明**: 記事の内容をまとめます。 通常、検索結果ページに表示されますが、検索ランキングには使用されません。 その長さはスペースを含めて 115-145 文字にする必要があります。
- **author**: author フィールドには、作成者の **GitHub ユーザー名**を含める必要があります。
- **ms.date**: 前回の大きな更新の日付です。 記事全体を見直し、更新している場合、既存の記事でこれを更新します。 誤植など、小さな修正の場合、更新されるとは限りません。

その他のメタデータは各記事に付け加えられますが、通常、ほとんどのメタデータ値は **docfx.json** に指定されているフォルダー レベルで適用されます。

## <a name="basic-markdown-gfm-and-special-characters"></a>基本的 Markdown、GFM、特殊文字

Markdown、GitHub Flavored Markdown (GFM)、OPS 固有の拡張機能の基本については、「[Markdown リファレンス](../markdown-reference.md)」の記事で学習できます。

Markdown では、書式設定に \*、\`、\# のような特殊文字が使用されます。 このような文字をコンテンツに含める場合、次の 2 つのいずれかを行う必要があります。

- 特殊文字の前にバックスラッシュを置いて "エスケープ処理" します (たとえば、\* の場合、`\*`)。
- その文字の [HTML エンティティ コード](http://www.ascii.cl/htmlcodes.htm)を使用します (たとえば、&#42; の場合、`&#42;`)。

## <a name="file-names"></a>ファイル名

ファイル名では次の規則が使用されます。

* 小文字、数字、ハイフンのみを含めることができます。
* 空白や句読点は使用できません。 ファイル名の単語と数値はハイフンを使用して区切ります。
* 動作を示す固有の動詞を使用します。develop、buy、build、troubleshoot などです。 進行形は使用しません。
* スモール ワード (a、and、the、in、or など) を含めてはなりません。
* Markdown フォーマットで、.md ファイル拡張子を使用する必要があります。
* ファイル名は無理のない範囲で短くします。 ファイル名は記事の URL の一部になります。

## <a name="headings"></a>見出し

文章スタイルで大文字と小文字を使い分けます。 見出しの最初の文字は必ず大文字にします。

## <a name="text-styling"></a>テキストのスタイル設定

*斜体* ファイル、フォルダー、パス (長い項目の場合、分割してそれだけの行にします)、新しい用語に使用します。

**太字** UI 要素に使用します。

`Code` インライン コード、言語キーワード、NuGet パッケージ名、コマンドライン コマンド、データベース テーブル、列名、クリック可能にしない URL に使用します。

## <a name="links"></a>リンク

アンカー、内部リンク、他のドキュメントのリンク、コード インクルード、外部リンクに関する詳細については、[リンク](../how-to-write-links.md)に関する全般記事をご覧ください。

.NET ドキュメント チームでは次の規則に従っています。

- ほとんどの場合、相対リンクを使用し、リンクに `~/` を使用することは奨励していません。相対リンクは GitHub のソースで解決されるためです。 ただし、依存レポジトリのファイルにリンクするときは必ず `~/` 文字を使用してパスを指定します。 依存レポジトリのファイルは GitHub の別の場所にあるため、記述方法に関係なく、相対リンクでは正しく解決されません。
- C# 言語仕様と Visual Basic 言語仕様は、言語リポジトリからソースを含めることにより .NET ドキュメントに含められます。 Markdown ソースは [csharplang](https://github.com/dotnet/csharplang) リポジトリと [vblang](https://github.com/dotnet/vblang) リポジトリで管理されます。

仕様のリンクは、その仕様が含まれるソース ディレクトリを指す必要があります。 以下の例にあるとおり、C# の場合は **~/_csharplang/spec** であり、VB の場合は **~/_vblang/spec** です。

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a>API のリンク

このビルド システムには、外部リンクを使用しなくても .NET API にリンクできる拡張機能があります。 次のいずれかの構文を使用します。

1. 自動リンク: `<xref:UID>` または `<xref:UID?displayProperty=nameWithType>`

   `displayProperty` クエリ パラメーターは、完全修飾のリンク テキストを生成します。 既定では、リンク テキストに表示されるのはメンバー名または型名のみです。

2. マークダウン リンク: `[link text](xref:UID)`

   表示されるリンク テキストをカスタマイズする場合に使用します。

例:

- `<xref:System.String>` は [String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます
- `<xref:System.String?displayProperty=nameWithType>` は [System.String](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます
- `[String class](xref:System.String)` は [String class](https://docs.microsoft.com/dotnet/api/system.string) としてレンダリングされます

この表記の使用について詳しくは、「[Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)」(相互参照の使用) を参照してください。

一部の UID には特殊文字 \`、\#、\* が含まれています。UID の値は、それぞれ `%60`、`%23`、`%2A` のように HTML エンコードする必要があります。 かっこがエンコードされている場合もありますが、これは必須ではありません。

例:

- System.Threading.Tasks.Task\`1 は、`System.Threading.Tasks.Task%601` になります
- System.Exception.\#ctor は、`System.Exception.%23ctor` になります
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) は、`System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` になります

型の UID、メンバー オーバーロード、特定のオーバーロードされたメンバーを `https://xref.docs.microsoft.com/autocomplete` から見つけることができます。 クエリ文字列 `?text=*\<type-member-name>*` では、UID を確認する型またはメンバーが特定されます。 たとえば、`https://xref.docs.microsoft.com/autocomplete?text=string.format` の場合、[String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) オーバーロードが取得されます。 このツールでは、指定された `text` クエリ パラメーターが UID のあらゆる部分で検索されます。 たとえば、メンバー名 (ToString)、部分的なメンバー名 (ToStri)、型とメンバーの名前 (Double.ToString) などを検索できます。

UID の後ろに \* (または `%2A`) を追加すると、リンクは固有の API ではなく、オーバーロードのページを表すようになります。 これはたとえば、[List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) のような固有のオーバーロードではなく、[List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) ページに汎用的な方法でリンクする必要がある場合に使用できます。 メンバーがオーバーロードされていないとき、\* を使用してメンバー ページにリンクすることもできます。それにより、UID にパラメーターの一覧を含める必要がなくなります。

特定のメソッド オーバーロードにリンクするには、メソッドの各パラメーターの完全修飾型名を含める必要があります。 たとえば、\<xref:System.DateTime.ToString> はパラメーターなしの [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) メソッドにリンクされますが、\<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> は [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) メソッドにリンクされます。

[System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) など、ジェネリック型にリンクするには、\` (`%60`) 文字にジェネリック型パラメーターの番号を続けます。 たとえば、`<xref:System.Nullable%601>` は [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 型にリンクされますが、`<xref:System.Func%602>`[System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) デリゲートにリンクされます。

## <a name="code"></a>コード

コードを含める最良の方法は、動作するサンプルからの抜粋を含めることです。 [.NET に協力する](dotnet-contribute.md#contributing-to-samples)方法に関する記事の指示に従い、サンプルを作成します。 コードを含める基本的規則は、[コード](../code-in-docs.md)の一般的なガイダンスにあります。

次の構文でコードを含めることができます。

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*省略可能*ですが、実施することを*お勧めします*)
  * 参照されているコード スニペットの言語。

* `<name>` (*省略可能*)
  * コード スニペットの名前。 出力 HTML には影響ありませんが、これを使用して Markdown ソースの読みやすさを向上させることができます。

* `<pathToFile>` (*必須*)
  * 参照するコード スニペット ファイルを示すファイル システムの相対パス。 これは .NET ドキュメント セットを構成するさまざまなレポジトリによって複雑になることがあります。 .NET サンプルは dotnet/samples レポジトリにあります。 すべてのスニペット パスは `~/samples` から始まり、パスの残りの部分はそのリポジトリのルートからソースまでのパスとなります。

* `<queryoption>` (*省略可能*)
  * ファイルからコードを取得する方法を指定するために使用。
    * `#`: `#{tagname}` (タグ名) *または* `#L{startlinenumber}-L{endlinenumber}` (行の範囲)。
    行番号は非常に崩れやすいため、使用はお勧めしません。 コード スニペットを参照する方法としてはタグ名をお勧めします。 タグ名には意味のある名前を使用します。 (スニペットの多くは前のプラットフォームから移行されており、タグには `Snippet1` や `Snippet2` のような名前が付けられています。この方法では保守管理が難しくなります。)
    * `range`:　`?range=1,3-5` 行の範囲です。 この例には、1、3、4、5 行が含まれます。

可能な限り、タグ名を使用することをお勧めします。 タグ名はリージョンまたはコード コメントの名前であり、ソース コードでは `Snippettagname` の形式で確認できます。 次の例は、タグ名 `BasicThrow` を参照する方法を示しています。

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

**dotnet/samples** レポジトリのソースの相対パスは `~/samples` パスに従います。

また、[このソース ファイル](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs)でスニペット タグの構造を確認できます。 言語別のコード スニペット ソース ファイルでのタグ名表現の詳細については、[DocFX ガイドライン](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)を参照してください。

次の例は、3 つすべての .NET 言語に含まれるコードを示しています。

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]
```

完全なプログラムからのスニペットを含めることで、すべてのコードが Microsoft の継続的インテグレーション (CI) システムで実行されます。 ただし、コンパイル タイム エラーまたはランタイム エラーの原因を表示する必要がある場合、インライン コード ブロックを使用できます。

## <a name="images"></a>イメージ

### <a name="static-image-or-animated-gif"></a>静止画像またはアニメーション GIF

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>リンク画像

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>ビデオ

現在のところ、Channel 9 動画と YouTube 動画をいずれも次の構文で埋め込むことができます。

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

動画の正しい URL を取得するには、動画フレームの下にある **[埋め込む]** タグを選択し、`<iframe>` 要素から URL をコピーします。 次に例を示します。

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

動画の正しい URL を取得するには、動画を右クリックし、 **[埋め込みコードのコピー]** を選択し、`<iframe>` 要素から URL をコピーします。

```markdown
> [!VIDEO <youtube_video_link>]
```

次に例を示します。

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>docs.microsoft 拡張機能

docs.microsoft では、GitHub Flavored Markdown の追加拡張機能をいくつか用意しています。

### <a name="checked-lists"></a>チェック済みリスト

カスタム スタイルはリストに使用できます。 緑のチェック マークを付けたリストをレンダリングできます。

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

これは次のようにレンダリングされます。

> [!div class="checklist"]
> * NET Core アプリの作成方法
> * Microsoft.XmlSerializer.Generator パッケージへの参照を追加する方法
> * MyApp.csproj を編集して依存関係を追加する方法
> * クラスと XmlSerializer を追加する方法
> * アプリケーションをビルドして実行する方法

[.NET Core ドキュメント](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)で、実際に使われているチェック済みリストの例を確認できます。

### <a name="buttons"></a>ボタン

ボタン リンク:

```markdown
> [!div class="button"]
> [button links](dotnet-contribute.md)
```

これは次のようにレンダリングされます。

> [!div class="button"]
> [ボタン リンク](dotnet-contribute.md)

[Visual Studio ドキュメント](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)で、実際に使われているボタンの例を確認できます。

### <a name="step-by-steps"></a>段階的手順

```markdown
>[!div class="step-by-step"]
> [Pre](../docs/csharp/expression-trees-interpreting.md)
> [Next](../docs/csharp/expression-trees-translating.md)
```

[C# ガイド](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)で、実際に使われている段階的手順の例を確認できます。
