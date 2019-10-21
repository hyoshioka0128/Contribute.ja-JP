---
title: docs.microsoft.com の Markdown 参照
description: Microsoft Docs プラットフォームで使われる Markdown の機能と構文について学習します。
author: meganbradley
ms.author: mbradley
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.openlocfilehash: 3142b1aee8cadb69f82bfbcd3f89c701fac5b356
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72288290"
---
# <a name="markdown-reference"></a>Markdown 参照

Markdown は、プレーン テキスト形式の構文を使用する軽量のマークアップ言語です。 Docs プラットフォームでは、Markdown の CommonMark 標準がサポートされているほか、docs.microsoft.com で豊富なコンテンツを提供する目的で設計されたカスタム Markdown 拡張機能も一部サポートされています。 この記事では、docs.microsoft.com で Markdown を使用するためのアルファベット順参照を提供します。

あらゆるテキスト エディターを使用して Markdown を作成できます。 標準の Markdown 構文とカスタム Docs 拡張機能の両方を簡単に挿入できるエディターとして、[Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) をインストールした [VS Code](https://code.visualstudio.com/) をお勧めします。

Docs では、Markdig Markdown エンジンが使用されます。 [https://babelmark.github.io/](https://babelmark.github.io/) では、Markdown のレンダリングを Markdig と他のエンジンで比較テストできます。

## <a name="alerts-note-tip-important-caution-warning"></a>アラート (Note, Tip, Important, Caution, Warning)

アラートは Docs Markdown の拡張機能です。これにより、コンテンツの重要性を示す色とアイコンを使用して docs.microsoft.com 上でレンダリングされるブロック引用が作成されます。 次の種類のアラートがサポートされています。

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

これらのアラートは docs.microsoft.com 上で次のように表示されます。

> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.

## <a name="code-snippets"></a>コード スニペット

Markdown ファイルにはコード スニペットを埋め込むことができます。

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>見出し

Docs では、6 つのレベルの Markdown 見出しがサポートされています。

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- 最後の `#` と見出しテキストの間にスペースを入れる必要があります。
- Markdown ファイルごとに与える H1 は 1 つだけにする必要があります。
- H1 は YML メタデータ ブロックの後ろに来る、ファイルで最初のコンテンツにする必要があります。
- H2 は右側に自動的に表示され、発行されたファイルのメニューのナビゲーションとなります。 これより下のレベルの見出しは表示されません。そのため、閲覧者がコンテンツを移動する支えになるように H2 を戦略的に利用してください。
- `<h1>` など、HMTL 見出しは推奨されません。場合によっては、ビルド警告を発生させます。
- [ブックマーク](#bookmark-links)を利用し、ファイル内で個別の見出しにリンクできます。

## <a name="html"></a>HTML

Markdown ではインライン HTML がサポートされていますが、Docs への公開には HTML は推奨されません。値の一覧が制限されていない限り、それによってビルドのエラーまたは警告が発生します。

## <a name="images"></a>イメージ

イメージをインクルードするための構文は次のようになります。

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

`alt text` はイメージの簡単な説明であり、`<folder path>` はイメージの相対パスです。 目が不自由な人のためにスクリーン リーダー用の代替テキストが必要になります。 イメージをレンダリングできないサイト バグがある場合にも役立ちます。

イメージはドキュメント セット内の `/media` フォルダーに格納してください。 イメージには既定で次の種類のファイルがサポートされています。

- .jpg
- .png

ドキュメント セットの docfx.json ファイルにリソースとして追加することで、他の種類のイメージのサポートを追加できます<!--add link to reference when available--> 。

## <a name="links"></a>リンク

多くの場合、Docs では、他のファイルやページへの標準の Markdown リンクが使用されます。 リンクの種類については、下のセクションに説明があります。

> [!TIP]
> Docs Authoring Pack for VS Code を利用すれば、パスを理解する面倒な作業なく、相対的なリンクとブックマークを正しく挿入できます。

> [!IMPORTANT]
> Microsoft サイトへのリンクに en-us のようなロケール コードを含めないでください。 ハードコーディングされたロケール コードはローカライズされたコンテンツのレンダリングを妨げます。他のロケールのお客様に不自由を与えることになり、また、大きなローカライズ コストを発生させます。 ブラウザーから URL をコピーすると、既定ではロケール コードが含まれます。そのため、リンクを作成するとき、手動で削除する必要があります。 たとえば、次のような URL を使用します。
>
> `[Microsoft](https://www.microsoft.com)`
>
> 次のような URL は使用しないでください。
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>同じドキュメント セットのファイルの相対リンク

相対パスとは、現在のファイルから見た目的のファイルまでのパスです。 Docs では、相対パスを使用することで、同じドキュメント セット内の別のファイルにリンクすることができます。 相対パスの構文は次のようになります。

```markdown
[link text](../../folder/filename.md)
```

`../` は階層で 1 つ上を示します。

- 相対パスはビルド中に解決されますが、その中で .md 拡張が削除されます。
- "../" を使用して親フォルダー内のファイルにリンクできますが、そのファイルは同じドキュメント セット内に置かれている必要があります。 "../" を使用して別のドキュメント セット フォルダー内のファイルにリンクすることはできません。
- Docs では、"~" で始まる特殊な形式の相対パスもサポートされています (~/foo/bar.md など)。 この構文は、ドキュメント セットのルート フォルダーから相対的に見たファイルを示しています。 この種類のパスも、ビルド中に検証および解決されます。

> [!IMPORTANT]
> 相対パスにファイル拡張子を含めてください。 その相対パスの目的ファイルの存在がビルドで検証されます。 相対パスにファイル拡張子が含まれない場合、ビルドにより、リンクが壊れていると警告されます。 たとえば、次のような URL を使用します。
>
> `[link text](../../folder/filename.md)`
>
> 次のような URL は使用しないでください。
>
> `[link text](../../folder/filename)`

### <a name="site-relative-links-to-other-files-on-docs"></a>Docs 上の他のファイルへのサイト相対リンク

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

ファイル拡張子 (.md) を含めません。 Azure "articles" ドキュメント セットの外から Linux 概要ファイルにリンクされています。

### <a name="links-to-external-sites"></a>外部サイトへのリンク

```markdown
[Microsoft](https://www.microsoft.com)
```

別の Web ページへの URL ベースのリンク (https:// を含める必要があります)。

### <a name="bookmark-links"></a>ブックマーク リンク

同じリポジトリにおける別ファイルの見出しへのブックマーク リンクは次のようになります。 次に例を示します。

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

現在のファイルにある見出しへのブックマーク リンクは次のようになります。

```markdown
[Managed Disks](#managed-disks)
```

ハッシュ記号 `#` に見出しの単語を続けて使用します。 見出しテキストをリンク テキストに変更するには、次の操作を行います。
- すべて小文字を使用する
- 句読点を削除する
- スペースをダッシュに置き換える

たとえば、見出しの名前が "2.2 Security concerns" の場合は、ブックマークのリンク テキストは "#22-security-concerns" になります。

### <a name="explicit-anchor-links"></a>明示的なアンカー リンク

`<a>` HTML タグを使用する明示的なアンカー リンクは、ハブ ページと待ち受けページを除き、**必須ではないか、推奨されません**。 一般的な Markdown ファイルでは、前述のブックマークを使用してください。 ハブ ページと待ち受けページについては、アンカーを次のように使用します。

`## <a id="AnchorText"> </a>Header text` または `## <a name="AnchorText"> </a>Header text`

明示的なアンカーにリンクするには、次の構文を使用します。

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>XREF (相互参照) リンク

現在のドキュメント セットまたは他のドキュメント セットにある自動生成 API 参照ページにリンクするには、一意の ID (UID) を持つ XREF リンクを使用します。

> [!NOTE]
> 他のドキュメント セットにある API 参照ページを参照するには、`docfx.json` ファイルで `xrefService` 構成を追加する必要があります。
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

UID は、クラスとメンバーの完全修飾名に相当します。 UID の後ろに * を追加すると、リンクは固有の API ではなく、オーバーロードのページを表すようになります。 たとえば、`List<T>.BinarySearch*` を使用すると、`List<T>.BinarySearch(T, IComparer<T>)` のような固有のオーバーロードにリンクする代わりに BinarySearch Method ページにリンクします。

次のいずれかの構文を使用できます。

- 自動リンク: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  任意の `displayProperty` クエリ パラメーターにより、完全修飾のリンク テキストが生成されます。 既定では、リンク テキストに表示されるのはメンバー名または型名のみです。

- マークダウン リンク: `[link text](xref:UID)`
  
  表示されるリンク テキストをカスタマイズする場合に使用します。

例:

- `<xref:System.String>` は "String" としてレンダリングされます。
- `<xref:System.String?displayProperty=nameWithType>` は "System.String" としてレンダリングされます。
- `[String class](xref:System.String)` は "String class" としてレンダリングされます。

現在、UID を検索する簡単な方法はありません。 <!-- ? -->API の UID を検索する最善の方法は、リンクする API のページのソースを表示し、ms.assetid という値を検索することです。 個別のオーバーロードの値は、ソースには表示されません。 将来的に、より優れたシステムを提供できるように取り組んでいます。

UID に特殊文字 \`、\#、\* が含まれている場合、UID の値は、それぞれ `%60`、`%23`、`%2A` のように HTML エンコードする必要があります。 かっこがエンコードされている場合もありますが、これは必須ではありません。

例:

- System.Threading.Tasks.Task\`1 は、`System.Threading.Tasks.Task%601` になります
- System.Exception.\#ctor は、`System.Exception.%23ctor` になります
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) は、`System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` になります

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>リスト (番号付き、箇条書き、チェックリスト)

### <a name="numbered-list"></a>番号付きリスト

番号付きリストを作成するには、すべての 1 を使用できます。これは公開されると、連続する一覧としてレンダリングされます。 ソースを読みやすくするために、リストをインクリメントできます。

入れ子になっているリストなど、リストには文字を使用しないでください。 Docs に公開するとき、それらは正しくレンダリングされません。番号を使用する入れ子リストは、公開されると、小文字としてレンダリングされます。 次に例を示します。

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

これは次のようにレンダリングされます。

1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)

### <a name="bulleted-list"></a>箇条書き

箇条書きを作成するには、`-` の後ろにスペースを入れてから各行を続けます。

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

これは次のようにレンダリングされます。

- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!

### <a name="checklist"></a>チェックリスト

チェックリストは、カスタム Markdown 拡張経由で docs.microsoft.com (のみ) で使用する場合に利用できます。

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

このサンプルは docs.microsoft.com で次のようにレンダリングされます。

> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3

"これから学習する内容" や "今回学習した内容" をまとめる目的で、記事の冒頭や最後でチェックリストを使用します。 記事全体でランダムなチェックリストを追加しないでください。
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>次のステップ アクション

カスタム拡張を使用し、次のステップ アクション ボタンを docs.microsoft.com (のみ) のページに追加できます。

構文は次のようになります。

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

次に例を示します。

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

これは次のようにレンダリングされます。

> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)

別の Web ページへの Markdown リンクを含め、次のステップ アクションでは、サポートされているあらゆるリンクを使用できます。 ほとんどの場合、次のアクション リンクは同じドキュメント セット内の別のファイルへの相対リンクになります。

## <a name="section-definition"></a>セクション定義

<!-- more info about this would be helpful! -->
セクションを定義する必要がある場合があります。 この構文は多くの場合、コード表に使用されます。
次の例を参照してください。

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

前述のブロック引用 Markdown テキストは、次のように表示されます。
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>セレクター

<!-- could be more clear! -->
同じ記事に対してさまざまなページをつなげる場合は、セレクターを使用できます。 閲覧者はページを切り替えることができます。

> [!NOTE]
> この拡張機能は、docs.microsoft.com と MSDN で機能が異なります。 <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>単一セレクター

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

これは次のようにレンダリングされます。

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>複数のセレクター

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

これは次のようにレンダリングされます。

> [!div class="op_multi_selector" title1="プラットフォーム" title2="バックエンド"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)

## <a name="tables"></a>表

Markdow で表を作成する最も簡単な方法は、パイプと行を使用することです。 ヘッダー付きの標準的な表を作成するには、最初の行の後に点線を続けます。

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

これは次のようにレンダリングされます。

|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!||

ヘッダーなしで表を作成することもできます。 たとえば、複数列のリストを作成するには、次の操作を行います。

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

これは次のようにレンダリングされます。

|   |   |
| - | - |
| This | table |
| has no | header |

コロンを使用して、列を整列することができます。

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

これは次のようにレンダリングされます。

|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|

> [!TIP]
> Docs Authoring Extension for VS Code では、基本的な Markdown 表を簡単に追加できます。
>
> [オンラインの表生成機能](http://www.tablesgenerator.com/markdown_tables)を使用することもできます。

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> これは docs.microsoft.com サイトでのみ機能します。

Markdown で表を作成すると、表が右側のナビゲーションまで広がって、表が読めなくなることがあります。 これは、必要に応じて、Docs のレンダリングで表内の改行を許可することで解決できます。 カスタム クラス `[!div class="mx-tdBreakAll"]` を使用して表を折り返すだけです。

クラス名が `mx-tdBreakAll` の `div` で折り返される 3 行の表の Markdown サンプルを次に示します。

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

これは次のようにレンダリングされます。

> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> これは docs.microsoft.com サイトでのみ機能します。

ときどき、表の 2 番目の列に非常に長い単語がある場合があります。 そのような単語を適切に分割するために、前述のような `div` ラッパー構文を使用して `mx-tdCol2BreakAll` クラスを適用できます。

### <a name="html-tables"></a>HTML テーブル

docs.microsoft.com の場合、HTML テーブルは推奨されません。 ソースでは人間が読めないようになっています。このことは Markdown の重要な原則の 1 つです。

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>動画

### <a name="embedding-videos-into-a-markdown-page"></a>Markdown ページに動画を埋め込む

現在、Docs では、次の 3 つの場所のいずれかに公開される動画がサポートされます。

- YouTube
- Channel 9
- Microsoft 独自の 'One Player' システム

次の構文を使用してビデオを埋め込むことができ、そのビデオは Docs でレンダリングされます。

```markdown
> [!VIDEO <embedded_video_link>]
```

例:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

これは次のようにレンダリングされます。

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

公開されたページでは、次のように表示されます。

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> CH9 ビデオの URL は `https` で始まり、`/player` で終わる必要があります。 そうしないと、ビデオだけでなくページ全体が埋め込まれます。

### <a name="uploading-new-videos"></a>新しい動画をアップロードする

新しい動画は次のプロセスでアップロードしてください。

1. IDWEB で **docs_video_users** グループに参加します。
1. [https://aka.ms/VideoUploadRequest](https://aka.ms/VideoUploadRequest ) に移動し、動画の詳細を入力します。 次の項目が必要になります (いずれも公開されません)。
    1. 動画のタイトル。
    1. 動画が関連する製品/サービスの一覧。
    1. 動画がホストされる対象ページまたは (ページをまだ用意していない場合) ドキュメント セット。
    1. 動画の MP4 ファイルへのリンク (ファイルを置く場所を用意していない場合、`\\scratch2\scratch\apex` に一時的に置くことができます)。 MP4 ファイルは 720p 以上にしてください。
    1. 動画の説明。
1. 項目を送信 (保存) します。
1. 2 営業日以内に動画がアップロードされます。 埋め込みに必要なリンクは作業項目に配置されます。解決されて*戻されます*。
1. 動画リンクを取得したら、作業項目を閉じます。
1. その後、次の構文を利用し、動画リンクを投稿に追加できます。

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
