---
title: docs.microsoft.com の Markdown 参照
description: Microsoft Docs プラットフォームで使われる Markdown の機能と構文について学習します。
author: meganbradley
ms.author: mbradley
ms.date: 03/31/2020
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.openlocfilehash: f0aed4ebb57ee1ce34f55d9085bab718fd4511cb
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "80624727"
---
# <a name="docs-markdown-reference"></a>Docs Markdown リファレンス

この記事では、docs.microsoft.com (Docs) で Markdown を記述するためのアルファベット順のリファレンスを提供します。

[Markdown](https://daringfireball.net/projects/markdown/) は、プレーン テキスト形式の構文を使用する軽量のマークアップ言語です。 Docs では、[Markdig](https://github.com/lunet-io/markdig) 解析エンジンを使って解析される [CommonMark](https://commonmark.org/) 準拠の Markdown がサポートされています。 Docs ではまた、より豊富なコンテンツを Docs サイトに提供するカスタム Markdown 拡張機能もサポートされています。

任意のテキスト エディターを使用して Markdown を記述できますが、[Visual Studio Code](https://code.visualstudio.com/) を [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) と共に使用することをお勧めします。 Docs Authoring Pack には編集ツールとプレビュー機能が用意されており、Docs に表示されたときの記事の外観を確認できます。

## <a name="alerts-note-tip-important-caution-warning"></a>アラート (Note, Tip, Important, Caution, Warning)

アラートは Markdown の拡張機能です。これにより、docs.microsoft.com 上でレンダリングされるブロック引用が、コンテンツの重要性を示す色とアイコンを使用して作成されます。 次の種類のアラートがサポートされています。

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

### <a name="angle-brackets"></a>山かっこ

プレースホルダーを示すためなどに、ファイル内のテキストに山かっこを使用する場合は、山かっこを手動でエンコードする必要があります。 そうしないと、それらのテキストは Markdown によって HTML タグとして認識されます。

たとえば、`<script name>` は `&lt;script name&gt;` または `\<script name>` としてエンコードします。

インライン コードとして、またはコード ブロック内に書式設定されたテキストでは、山かっこをエスケープする必要はありません。

## <a name="apostrophes-and-quotation-marks"></a>アポストロフィと引用符

Word から Markdown エディターにコピーしたテキストに、"スマート" (カールした) アポストロフィまたは引用符が含まれていることがあります。 これらを標準的なアポストロフィや引用符にエンコードまたは変更する必要があります。 そうしないと、ファイルが公開されたときに次のように表示されます: Itâ&euro;&trade;s

これらの "スマート" バージョンの記述記号のエンコーディングは次のとおりです。

- 左 (始め) 二重引用符: `&#8220;`
- 右 (終わり) 二重引用符: `&#8221;`
- 右 (終わり) 一重引用符またはアポストロフィ: `&#8217;`
- 左 (始め) 一重引用符 (あまり使用されません): `&#8216;`

## <a name="blockquotes"></a>ブロック引用

ブロック引用は `>` 文字で作成されます。

```md
> This is a blockquote. It is usually rendered indented and with a different background color.
```

先の例は次のようにレンダリングされます。

> これはブロック引用です。 通常は、インデントされ、別の背景色で表示されます。

## <a name="bold-and-italic-text"></a>太字や斜体のテキスト

テキストの書式を**太字**に設定するには、テキストを二重のアスタリスクで囲みます。

```markdown
This text is **bold**.
```

テキストの書式を*斜体*に設定するには、テキストを一重のアスタリスクで囲みます。

```markdown
This text is *italic*.
```

テキストの書式を***太字と斜体***の両方に設定するには、テキストを三重のアスタリスクで囲みます。

```markdown
This text is both ***bold and italic***.
```

## <a name="code-snippets"></a>コード スニペット

Docs Markdown では、コード スニペットの配置方法として、文中へのインライン配置と、文と文の間への "フェンスされた" 個別ブロックとしての配置の両方がサポートされます。 詳細については、「[ドキュメントにコードを追加する方法](code-in-docs.md)」を参照してください。

## <a name="columns"></a>列

Markdown 拡張機能の**列**を使用すると、ドキュメントの作成者は、基本的な Markdown テーブルよりも柔軟で強力な列ベースのコンテンツ レイアウトを追加できます (基本的な Markdown テーブルは実際に表形式であるデータのみに適しています)。 最大 4 つの列を追加し、オプションの `span` 属性を使用して 2 つ以上の列を結合できます。

列の構文は次のようになります。

```markdown
:::row:::
   :::column span="":::
      Content...
   :::column-end:::
   :::column span="":::
      More content...
   :::column-end:::
:::row-end:::
```

列には、画像を含めた基本的な Markdown のみを挿入する必要があります。 見出し、テーブル、タブ、およびその他の複雑な構造を含めることはできません。 行で列の外部にコンテンツを含めることはできません。

たとえば、次の Markdown では、幅が 2 列にまたがる 1 個の列と、1 個の標準 (`span` なし) 列が作成されます。

```markdown
:::row:::
   :::column span="2":::
      **This is a 2-span column with lots of text.**

      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vestibulum mollis nunc
      ornare commodo. Nullam ac metus imperdiet, rutrum justo vel, vulputate leo. Donec
      rutrum non eros eget consectetur.
   :::column-end:::
   :::column span="":::
      **This is a single-span column with an image in it.**

      ![Doc.U.Ment](media/markdown-reference/document.png)
   :::column-end:::
:::row-end:::
```

これは次のようにレンダリングされます。

:::row:::
   :::column span="2":::
      **This is a 2-span column with lots of text.**

      Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Donec vestibulum mollis nunc ornare commodo.  Nullam ac metus imperdiet, rutrum justo vel, vulputate leo.  Donec rutrum non eros eget consectetur.
   :::column-end:::
   :::column span="":::
      **This is a single-span column with an image in it.**

      ![Doc.U.Ment](media/markdown-reference/document.png)
   :::column-end:::
:::row-end:::

## <a name="headings"></a>見出し

Docs では、6 つのレベルの Markdown 見出しがサポートされています。

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- 最後の `#` と見出しテキストの間にスペースを入れる必要があります。
- 各 Markdown ファイルに H1 見出しは 1 つだけ含まれている必要があります。
- H1 見出しは YML メタデータ ブロックの後ろに来る、ファイルで最初のコンテンツにする必要があります。
- H2 見出しは、公開されたファイルの右側のナビゲーション メニューに、自動的に表示されます。 これより下のレベルの見出しは表示されません。そのため、閲覧者がコンテンツ内を移動しやすくなるように、H2 を戦略的に利用してください。
- `<h1>` などの HTML 見出しは推奨されません。場合によっては、ビルド警告が発生します。
- [ブックマーク リンク](how-to-write-links.md#explicit-anchor-links)を使用して、ファイル内の個々の見出しにリンクすることができます。

## <a name="html"></a>HTML

Markdown ではインライン HTML がサポートされていますが、Docs への公開には HTML は推奨されません。値の一覧が限られている場合を除き、ビルドのエラーまたは警告が発生します。

## <a name="images"></a>イメージ

イメージには既定で次の種類のファイルがサポートされています。

- .jpg
- .png

### <a name="standard-conceptual-images-default-markdown"></a>標準の概念図 (既定の Markdown)

画像を埋め込むための基本的な Markdown 構文は次のとおりです。

```Markdown
![<alt text>](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

`<alt text>` はイメージの簡単な説明であり、`<folder path>` はイメージの相対パスです。 目が不自由な人のためにスクリーン リーダー用の代替テキストが必要になります。 画像をレンダリングできないサイト バグがある場合にも役立ちます。

alt テキスト内のアンダースコアは、前に円記号を付けてエスケープする (`\_`) 必要があります。そうしないと正しくレンダリングされません。 ただし、alt テキストとして使用するためにファイル名をコピーしないでください。 たとえば、次のようにするのではなく、

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

次のように記述します。

```markdown
![Active Directory extension for two-factor authentication, step 4: Configure](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="standard-conceptual-images-docs-markdown"></a>標準の概念図 (Docs Markdown)

Docs カスタム拡張機能の `:::image:::` では、標準の画像、複雑な画像、アイコンがサポートされています。

標準の画像の場合、以前の Markdown 構文は引き続き機能しますが、新しい拡張機能をお勧めします。新しい拡張機能では、親トピックとは異なるローカライズ スコープの指定など、より強力な機能がサポートされているためです。 ローカル画像を指定する代わりに共有イメージ ギャラリーから選択するなど、その他の高度な機能が今後使用できるようになります。 新しい構文は次のとおりです。

```Markdown
:::image type="content" source="<folderPath>" alt-text="<alt text>":::
```

`type="content"` (既定値) の場合、`source` と `alt-text` は必須です。

### <a name="complex-images-with-long-descriptions"></a>長い説明を含む複雑な画像

また、この拡張機能を使用すると、スクリーン リーダーによって読み上げられる、公開されたページに視覚的に表示されない長い説明を含む画像を追加することもできます。 長い説明は、グラフなどの複雑な画像に求められるアクセシビリティの要件です。 構文は次のとおりです。

```Markdown
:::image type="complex" source="<folderPath>" alt-text="<alt text>":::
   <long description here>
:::image-end:::
```

`type="complex"`、`source`、`alt-text`、長い説明、`:::image-end:::` タグは、すべて必須です。

### <a name="specifying-loc-scope"></a>ローカライズ スコープの指定

画像のローカライズ スコープが、その画像を含む記事またはモジュールのローカライズ スコープと異なる場合があります。 これにより、間違ったグローバル エクスペリエンスが発生する可能性があります。たとえば、製品のスクリーンショットが、その製品を利用可能でない言語に誤ってローカライズされる場合があります。 これを回避するには、種類が `content` および `complex` の画像にオプションの `loc-scope` 属性を指定します。

### <a name="icons"></a>アイコン

画像拡張機能では、アイコンがサポートされています。アイコンは装飾的な画像であり、alt テキストを使用することはできません。 アイコンの構文は次のとおりです。

```Markdown
:::image type="icon" source="<folderPath>":::
```

`type="icon"` の場合、`source` のみを指定する必要があります。

## <a name="included-markdown-files"></a>インクルードされた Markdown ファイル

Markdown ファイルを複数の記事で繰り返す必要がある場合は、インクルード ファイルを使用できます。 インクルード機能により、ビルド時に参照をインクルード ファイルの内容に置き換えるように Docs に指示します。 インクルードは、次の方法で使用できます。

- インライン: 一般的なテキスト スニペットを文中にインラインで再利用できます。
- ブロック: Markdown ファイル全体をブロックとして再利用し、記事のセクション内にネストできます。

インラインまたはブロックによるインクルード ファイルは、Markdown (.md) ファイルです。 これにはあらゆる有効な Markdown を含めることができます。 インクルード ファイルは、通常、リポジトリのルートにある *includes* 共通サブディレクトリ内に配置されます。 記事が公開されると、インクルードされたファイルはその記事にシームレスに統合されます。

### <a name="includes-syntax"></a>インクルード構文

ブロック インクルードは、独立した行でのインクルードです。

```markdown
[!INCLUDE [<title>](<filepath>)]
```

インライン インクルードは、行の内部でのインクルードです。

```markdown
Text before [!INCLUDE [<title>](<filepath>)] and after.
```

ここで `<title>` はファイルの名前、`<filepath>` はファイルへの相対パスです。 `INCLUDE` は大文字にする必要があり、`<title>` の前にスペースが必要です。

インクルード ファイルに関する要件と考慮事項を次に示します。

- ブロックによるインクルードは、1 つまたは 2 つの段落、共通の手順、共通のセクションといった分量の多いコンテンツに使用してください。 1 つの文よりも小さい場合には、使用しないでください。
- インクルードは Docs 拡張機能に依存するため、GitHub でレンダリングした記事にインクルードはレンダリングされません。 公開後にのみレンダリングされます。
- インクルード ファイル内のすべてのテキストの記述には、インクルードを参照する記事内の先行テキストや後続テキストに依存しない完全な文または語句を使用してください。 このガイダンスを無視すると、翻訳不可能な文字列が記事内に発生します。
- インクルード ファイルを他のインクルード ファイル内に埋め込まないでください。
- メディア ファイルは、インクルードのサブディレクトリ内にあるメディア フォルダーに配置する必要があります。たとえば、`<repo>` */includes/media* フォルダーです。 *media* ディレクトリのルートには画像を配置しないでください。 画像がないインクルードの場合は、対応する *media* ディレクトリは不要です。
- 通常の記事と同様に、インクルード ファイル間でメディアを共有しないでください。 インクルードおよび記事ごとに、一意の名前を持つ個別ファイルを使用してください。 インクルードに関連するメディア フォルダー内にメディア ファイルを格納してください。
- 記事の唯一のコンテンツとしてインクルードを使用しないでください。  インクルードの目的は、記事内のほかのコンテンツを補完することです。

## <a name="links"></a>リンク

リンクの構文の詳細については、「[ドキュメントでリンクを使用する](how-to-write-links.md)」を参照してください。

## <a name="lists-numbered-bulleted-checklist"></a>リスト (番号付き、箇条書き、チェックリスト)

### <a name="numbered-list"></a>番号付きリスト

番号付きリストを作成するには、すべて 1 を使用できます。 数値は、公開時には連続したリストとして昇順にレンダリングされます。 ソースを読みやすくするために、リストを手動でインクリメントできます。

入れ子になっているリストを含めて、リストには文字を使用しないでください。 Docs に公開したとき、それらは正しくレンダリングされません。番号を使用する入れ子リストは、公開されると、小文字としてレンダリングされます。 次に例を示します。

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

箇条書きを作成するには、`-` または `*` の後ろにスペースを入れてから各行を続けます。

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

`-` と `*` のどちらの構文を使用する場合も、それを記事内で一貫して使用してください。

### <a name="checklist"></a>チェックリスト

チェックリストは、カスタム Markdown 拡張機能を使って Docs で使用する場合に利用できます。

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

この例は Docs 上に次のようにレンダリングされます。

> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3

"これから学習する内容" や "今回学習した内容" をまとめる目的で、記事の冒頭や最後でチェックリストを使用します。 記事全体でランダムなチェックリストを追加しないでください。

## <a name="next-step-action"></a>次のステップ アクション

カスタム拡張機能を使用して、次のステップ アクション ボタンを Docs のページに追加できます。

構文は次のようになります。

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

次に例を示します。

```markdown
> [!div class="nextstepaction"]
> [Learn about adding code to articles](code-in-docs.md)
```

これは次のようにレンダリングされます。

> [!div class="nextstepaction"]
> [Learn about adding code to articles](code-in-docs.md)

別の Web ページへの Markdown リンクを含め、次のステップ アクションでは、サポートされているあらゆるリンクを使用できます。 ほとんどの場合、次のアクション リンクは同じドキュメント セット内の別のファイルへの相対リンクになります。

## <a name="non-localized-strings"></a>ローカライズされない文字列

カスタム Markdown 拡張機能の `no-loc` を使用して、ローカライズ プロセスで無視するコンテンツの文字列を識別できます。

呼び出されるすべての文字列は、大文字と小文字が区別されます。つまり、文字列がローカライズで無視されるためには、正確に一致する必要があります。

個々の文字列をローカライズ不可としてマークするには、次の構文を使用します。

```markdown
:::no-loc text="String":::
```

たとえば次の場合、ローカライズ プロセスで `Document` の 1 つのインスタンスのみが無視されます。

```markdown
# Heading 1 of the Document

Markdown content within the :::no-loc text="Document":::.  The are multiple instances of Document, document, and documents.
```

> [!NOTE]
> 特殊文字をエスケープするには `\` を使用します。
> ```markdown
> Lorem :::no-loc text="Find a \"Quotation\""::: Ipsum.
> ```

YAML ヘッダーのメタデータを使用して、現在の Markdown ファイル内で任意の文字列のすべてのインスタンスをローカライズ不可としてマークすることもできます。

```yml
author: cillroy
no-loc: [Global, Strings, to be, Ignored]
```

> [!NOTE]
> *docfx. json* ファイル内のグローバル メタデータとして、no-loc メタデータはサポートされていません。 ローカライズ パイプラインでは *docfx. json* ファイルが読み取られないため、個々のソース ファイルのそれぞれに no-loc メタデータを追加する必要があります。

次の例では、メタデータ `title` と Markdown ヘッダーの両方で、`Document` という単語がローカライズ プロセスで無視されます。

メタデータ `description` と Markdown のメイン コンテンツでは、`document` という単語がローカライズされています。これは、大文字 `D` で始まっていないためです。

```markdown
---
title: Title of the Document
author: author-name
description: Description for the document
no-loc: [Title, Document]
---
# Heading 1 of the Document

Markdown content within the document.
```

<!-- commenting out for now because no one knows what this means
## Section definition

You might need to define a section. This syntax is mostly used for code tables.
See the following example:

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

The preceding blockquote Markdown text will be rendered as:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
-->

## <a name="selectors"></a>セレクター

セレクターは、同じ記事の複数のフレーバーをユーザーが切り替えられるようにする UI 要素です。 一部のドキュメント セットにおいて、テクノロジまたはプラットフォーム間の実装の違いに対処するために使用されます。 一般的に、セレクターが最も当てはまるのは、開発者向けのモバイル プラットフォームのコンテンツです。

セレクターを使用する各記事ファイルに配置されるセレクター Markdown は同じであるため、ご自分の記事のセレクターをインクルード ファイル内に配置することをお勧めします。 そのうえで、同じセレクターを使用するご自分のすべての記事ファイル内で、そのインクルード ファイルを参照できます。

セレクターには単一セレクターと複数のセレクターの 2 種類があります。

### <a name="single-selector"></a>単一セレクター

```markdown
> [!div class="op_single_selector"]
> - [Universal Windows](../articles/notification-hubs-windows-store-dotnet-get-started/)
> - [Windows Phone](../articles/notification-hubs-windows-phone-get-started/)
> - [iOS](../articles/notification-hubs-ios-get-started/)
> - [Android](../articles/notification-hubs-android-get-started/)
> - [Kindle](../articles/notification-hubs-kindle-get-started/)
> - [Baidu](../articles/notification-hubs-baidu-get-started/)
> - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
> - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)
```

これは次のようにレンダリングされます。

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-links.md)
> - [Windows Phone](how-to-write-links.md)
> - [iOS](how-to-write-links.md)
> - [Android](how-to-write-links.md)
> - [Kindle](how-to-write-links.md)
> - [Baidu](how-to-write-links.md)
> - [Xamarin.iOS](how-to-write-links.md)
> - [Xamarin.Android](how-to-write-links.md)

### <a name="multi-selector"></a>複数のセレクター

```markdown
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
> - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
> - [(Windows universal C# | .NET)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
> - [(Windows universal C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
> - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
> - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
> - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
> - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
> - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
> - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)
```

これは次のようにレンダリングされます。

> [!div class="op_multi_selector" title1="プラットフォーム" title2="バックエンド"]
> - [(iOS | .NET)](how-to-write-links.md)
> - [(iOS | JavaScript)](how-to-write-links.md)
> - [(Windows universal C# | .NET)](how-to-write-links.md)
> - [(Windows universal C# | Javascript)](how-to-write-links.md)
> - [(Windows Phone | .NET)](how-to-write-links.md)
> - [(Windows Phone | Javascript)](how-to-write-links.md)
> - [(Android | .NET)](how-to-write-links.md)
> - [(Android | Javascript)](how-to-write-links.md)
> - [(Xamarin iOS | Javascript)](how-to-write-links.md)
> - [(Xamarin Android | Javascript)](how-to-write-links.md)

## <a name="subscript-and-superscript"></a>添字と上付き文字

添字または上付き文字は、数式について記述する場合など、技術的な正確性のために必要な場合に限って使用してください。 脚注など、標準以外のスタイルでは使用しないでください。

添字と上付き文字の両方について、HTML を使用します。

```html
Hello <sub>This is subscript!</sub>
```

これは次のようにレンダリングされます。

Hello <sub>This is subscript!</sub>

```html
Goodbye <sup>This is superscript!</sup>
```

これは次のようにレンダリングされます。

Goodbye <sup>This is superscript!</sup>

## <a name="tables"></a>Tables

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

コロンを使用して、列を整列することができます。

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

これは次のようにレンダリングされます。

| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

> [!TIP]
> Docs Authoring Extension for VS Code では、基本的な Markdown 表を簡単に追加できます。
>
> [オンラインの表生成機能](http://www.tablesgenerator.com/markdown_tables)を使用することもできます。

### <a name="line-breaks-within-words-in-any-table-cell"></a>任意のテーブル セルでの単語内の改行

Markdown テーブルに長い単語があると、テーブルが右側のナビゲーションまで広がって読めなくなることがあります。 これを解決するには、Docs のレンダリングで必要に応じて単語内に改行を自動的に挿入できるようにします。 カスタム クラス `[!div class="mx-tdBreakAll"]` を使用して表を折り返すだけです。

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

### <a name="line-breaks-within-words-in-second-column-table-cells"></a>2 番目の列のテーブル セルでの単語内の改行

テーブルの 2 番目の列のみで、単語内に改行を自動的に挿入することもできます。 改行を 2 番目の列に限定するには、前に示した `div` のラッパー構文を使用して `mx-tdCol2BreakAll` クラスを適用します。

### <a name="data-matrix-tables"></a>データ マトリックス テーブル

データ マトリックス テーブルには、ヘッダーと重み付けされた最初の列の両方が備わり、左上に空のセルがあるマトリックスが作成されます。 Docs には、データ マトリックス テーブル用のカスタム Markdown が用意されています。

```md
|                  |Header 1 |Header 2|
|------------------|---------|--------|
|**First column A**|Cell 1A  |Cell 2A |
|**First column B**|Cell 1B  |Cell 2B |
```

最初の列に含まれるすべてのエントリは、太字 (`**bold**`) としてスタイル設定する必要があります。そうしないと、スクリーン リーダーからテーブルにアクセスできず、Docs でテーブルが有効になりません。

### <a name="html-tables"></a>HTML テーブル

docs.microsoft.com の場合、HTML テーブルは推奨されません。 それらはソースで人間が判読できるようになっていません。このことは Markdown の重要な原則の 1 つです。
