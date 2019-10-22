---
title: PowerShell 記事のテンプレートとチートシート
description: この記事には、PowerShell ドキュメント用の新しい記事を作成するときに使用できる便利なテンプレートが含まれています
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: sdwheeler
ms.author: sewhee
ms.date: 10/09/2019
ms.openlocfilehash: e7ee9295794adfde78a2d500f0de3309dd3c821a
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72290359"
---
# <a name="markdown-style-guide-for-powershell-docs"></a>PowerShell-Docs の Markdown スタイル ガイド

この記事では、PowerShell-Docs コンテンツに固有のスタイル ガイダンスをいくつか紹介します。

他の記述スタイル ガイダンスについては、[Microsoft スタイル ガイド](https://docs.microsoft.com/style-guide/welcome/)を参照してください。

## <a name="metadata"></a>メタデータ

このテンプレートには、Markdown 構文の例とメタデータの設定方法が含まれています。
Markdown ファイルを作成するとき、付属のテンプレートを新しいファイルにコピーし、下のようにメタデータに入力し、上の H1 見出しを記事のタイトルに設定してください。

必須のメタデータ ブロックは次のサンプル メタデータ ブロックにあります。

```md
---
author: [GITHUB USERNAME]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
title: [ARTICLE TITLE]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- コロン (:) とメタデータ要素の値の間にはスペースを入れる**必要があります**。
- 値 (タイトルなど) 内のコロンによってメタデータ パーサーが中断されます。 その場合、タイトルを二重引用符で囲みます (例: `title: "Writing .NET Core console apps: An advanced step-by-step guide"`)。
- **author**: author フィールドには、作成者の **GitHub ユーザー名**を含める必要があります。
- **説明**: 記事の内容をまとめます。 通常、検索結果ページに表示されますが、検索ランキングには使用されません。 その長さはスペースを含めて 115-145 文字にする必要があります。
- **ms.date**: 前回の大きな更新の日付です。 記事全体を見直し、更新している場合、既存の記事でこれを更新します。 誤植など、小さな修正の場合、更新されるとは限りません。
- **title**: 検索エンジンの結果に表示されます。 タイトルは H1 見出しのタイトルと同じにしないでください。また、60 文字以下にする必要があります。

その他のメタデータは各記事に付け加えられますが、通常、ほとんどのメタデータ値は **docfx.json** に指定されているフォルダー レベルで適用されます。

## <a name="product-terminology"></a>製品の用語

PowerShell にはいくつかのバリエーションがあります。 この表では、PowerShell について説明するために使用されるさまざまな用語の一部を定義します。

- **PowerShell** - これが既定です。 PowerShell は弊社が出荷する製品です。 PowerShell という用語は、製品の任意のエディションを説明するために使用できます。
- **PowerShell Core** - サポートされる任意のプラットフォームの .NET Core 共通言語ランタイム (CoreCLR) 上に構築された PowerShell。
- **Windows PowerShell** - .NET Framework 共通言語ランタイム (CLR) 上に構築された PowerShell。 Windows PowerShell は Windows にのみ付属しており、完全な .Net Framework CLR が必要です。

一般に、ドキュメントで "Windows PowerShell" となっている箇所は、"PowerShell" に変更できます。
Windows 固有のテクノロジについて説明されている場合は、"Windows PowerShell" を変更することは**できません**。

## <a name="basic-markdown-gfm-and-special-characters"></a>基本的 Markdown、GFM、特殊文字

Markdown、GitHub Flavored Markdown (GFM)、OPS 固有の拡張機能の基本については [Markdown](../how-to-write-use-markdown.md) と [Markdown リファレンス](../markdown-reference.md)に関する全般記事で学習できます。

Markdown では、書式設定に \*、\`、\# のような特殊文字が使用されます。 このような文字をコンテンツに含める場合、次の 2 つのいずれかを行う必要があります。

- 特殊文字の前にバックスラッシュを置いて "エスケープ処理" します (たとえば、\* の場合、`\*`)。
- その文字の [HTML エンティティ コード](http://www.ascii.cl/htmlcodes.htm)を使用します (たとえば、&#42; の場合、`&#42;`)。
- マークダウン ファイルでは、プレーン ASCII テキストまたは UTF-8 エンコードを使用する必要があります。 ただし、複数バイトの UTF-8 文字は使用しないでください。 代わりに、HTML エンティティを使用します。 たとえば、著作権記号には `&copy;` を使用します。
  それは "&copy;" のように表示されます。

## <a name="hyperlinks"></a>ハイパーリンク

- URL をそのまま使用しないでください。 リンクには Markdown 構文 `[friendlyname](url-or-path)` を使用する必要があります
- リンクにはフレンドリ名が必要です。通常はリンク先のトピックのタイトルです
- 下部にある "関連リンク" セクションのすべての項目には、ハイパーリンクを設定する必要があります。
- **docs.microsoft.com** でホストされている他のコンテンツにリンクするときは、相対リンクを使用します。
- ハイパーリンクの角かっこ内には、バッククォート、太字、または他のマークアップを使用しないでください。

リンクの詳細については、「[ドキュメントでリンクを使用する](../how-to-write-links.md)」を参照してください。

## <a name="filenames"></a>ファイル名

ファイル名では次の規則が使用されます。

- 文字、数字、ハイフンのみを使用します。
- 空白や句読点は使用できません。 ファイル名の単語と数値はハイフンを使用して区切ります。
- 動作を示す固有の動詞を使用します。develop、buy、build、troubleshoot などです。 進行形は使用しません。
- スモール ワード (a、and、the、in、or など) を含めてはなりません。
- Markdown フォーマットで、.md ファイル拡張子を使用する必要があります。
- ファイル名は無理のない範囲で短くします。 ファイル名は記事の URL の一部になります。

## <a name="blank-lines-spaces-and-tabs"></a>空白行、スペース、およびタブ

重複する空白行を削除します。 複数の空白行は HTML では単一の空白行として表示されるため、複数の空白行にする意味がありません。

空白行は、Markdown 内のブロックの終わりも示します。 異なる種類の Markdown ブロックの間には、1 つの空白が必要です (たとえば、段落とリストまたはヘッダーの間)。

> [!NOTE]
> Markdown では、スペースは重要です。 ハード タブではなくスペースを常に使用します。 行の末尾にある余分なスペースを削除します。

## <a name="titles-and-headings"></a>タイトルと見出し

[ATX 見出し][atx]だけを使用します (`=` または `-` スタイルのヘッダーではなく、# スタイル)。

- 文頭のみ大文字を使用する - 適切な名詞およびタイトルまたはヘッダーの最初の文字だけを大文字にする必要があります
- `#` と見出しの最初の文字の間には、1 つのスペースが必要です
- 見出しは 1 つの空白行で囲む必要があります
- ドキュメントあたり 1 つだけの H1
- ヘッダー レベルは 1 ずつインクリメントする必要があります。レベルをスキップしないでください
- ヘッダーでは、バッククォート、太字、または他のマークアップを使用しないでください

> [!CAUTION]
> コマンドレット リファレンス用の [PlatyPS][platyPS] によって適用されるスキーマには、特定の H2 および H3 ヘッダーが必要です。 ヘッダーを追加または削除すると、ビルドが中断される可能性があります。 詳細については、[コマンドレット リファレンス スタイル ガイド](powershell-style-reference.md)を参照してください。

## <a name="limit-line-length-to-100-characters"></a>行の長さを 100 文字に制限します

これにより、差分および履歴のコマンドライン出力が簡略化されます。

このルールは PowerShell-Docs の既存コンテンツの多くには適用されていませんが、少しずつ作業を進めています。 ぜひお試しください。Visual Studio Code (VSCode) の[リフロー拡張機能][reflow]を使用すると、段落をこの制限に簡単に再フォーマットできます。

## <a name="lists"></a>リスト

リストに複数の文または段落が含まれている場合は、リストではなくサブレベル ヘッダーの使用を検討してください。

リストは 1 つの空白行で囲む必要があります。

### <a name="unordered-lists"></a>順不同のリスト

複数の文が含まれている場合を除き、ピリオドでリスト項目を終了しないでください。 リスト項目の箇条書きには、ハイフン文字 (`-`) を使用します。 これにより、アスタリスク (`*`) を使用する、太字または斜体のマークアップとの混同を回避できます。 段落またはその他の要素を箇条書き項目の下に含めるには、改行を挿入し、インデントを行頭文字の後の最初の文字に揃えます。

次に例を示します。

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

これは、箇条書き項目の下にサブ要素が含まれているリストです。

- 1 番目の箇条書き項目

  1 番目の箇条書きを説明する文。

  - サブ箇条書き項目

    サブ箇条書きを説明する文。

- 2 番目の箇条書き項目
- 3 番目の箇条書き項目

### <a name="ordered-lists"></a>順序指定されたリスト

段落またはその他の要素を番号付き項目の下に含めるには、インデントを項目番号の後の最初の文字に揃えます。

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

この出力を取得するには:

> 1. 1 番目の要素では、1 の後に 1 個のスペースを挿入します。 長い文は次の行に折り返す必要があり、番号付きリスト マーカーの後の最初の文字に揃えて配置する必要があります。
>
>    2 番目の要素 (これのような要素) を含めるには、1 番目の後に改行を挿入し、インデントを配置します。 2 番目の要素のインデントは、番号付きリスト マーカーの後の最初の文字と揃える必要があります。 これのような 1 桁の項目では、列 4 にインデントします。 2 桁の項目の場合は (項目番号 10 など)、列 5 にインデントします。
>
> 1. 次の番号付き項目はここから始まります。

番号付きリストのすべての項目は、項目ごとにインクリメントするのではなく、`1.` を使用する必要があります。
Markdown のレンダリングでは、値が自動的にインクリメントされます。 これにより、項目の並べ替えが簡単になり、下位のコンテンツのインデントが標準化されます。

## <a name="formatting-command-syntax-elements"></a>コマンド構文要素の書式設定

- PowerShell コマンドレットの名前は[パスカル ケース][pascal-case]です。 動詞と名詞はハイフンで区切られています。 コマンドレットとパラメーターには、常に完全なパスカル ケースを使用します。 別名について特に説明する場合を除き、別名の使用は避けてください。

- 段落内では、言語キーワード、コマンドレット名、および変数参照は、バッククォート (`` ` ``) 文字で囲む必要があります。 プロパティ名、パラメーター名、およびクラス名は、**太字**にする必要があります。

  次に例を示します。

  ~~~markdown
  The following code assigns the output of `Get-ChildItem` to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

- 名前でパラメーターを参照する場合、名前は**太字**にする必要があります。 パラメーターをハイフン プレフィックスと共に使用する場合は、パラメーターをバッククォートで囲む必要があります。 次に例を示します。

  ```markdown
  The parameter's name is **Name**, but it is typed as `-Name` when used on the command
  line as a parameter.
  ```

- 外部コマンド (EXE、スクリプトなど) を参照する場合は、コマンド名を太字、すべて小文字 (または文の先頭にある場合は大文字) にし、適切なファイル拡張子を含める必要があります。 次に例を示します。

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- 外部コマンドの使用例を示す場合は、例をバッククォートで囲む必要があります。
  別名と名前の競合がある場合は、コマンドの例にファイル拡張子を含める必要があります。 次に例を示します。

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- 概念説明の記事 (リファレンス コンテンツではなく) を記述する場合は、コマンドレット名の最初のインスタンスをコマンドレットのドキュメントにハイパーリンクする必要があります。 ハイパーリンクの角かっこ内には、バッククォート、太字、または他のマークアップを使用しないでください。

  次に例を示します。

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  詳細については、スタイル ガイドの「[ハイパーリンク](#hyperlinks)」セクションを参照してください。

## <a name="images"></a>イメージ

イメージをインクルードするための構文は次のようになります。

```Syntax
![[alt text]](<folderPath>)
```

例:

```markdown
![Introduction](./media/overview/Introduction.png)
```

`alt text` はイメージの簡単な説明であり、`<folder path>` はイメージの相対パスです。 目が不自由な人のためにスクリーン リーダー用の代替テキストが必要になります。 イメージをレンダリングできないサイト バグがある場合にも役立ちます。

イメージは、記事が格納されているフォルダー内の `media/<article-name>` フォルダーに格納する必要があります。 イメージを記事間で共有することはできません。 `media` フォルダーの下に、記事のファイル名と一致するフォルダーを作成します。 その記事のイメージをその新しいフォルダーにコピーします。 複数の記事でイメージが使用されている場合は、各イメージ フォルダーにそのイメージ ファイルのコピーを含める必要があります。 これにより、ある記事でイメージを変更しても、別の記事に影響を与えることがなくなります。

場合によっては、ロゴやアイコンのように、イメージを複数の記事で共有することもできます。 このようなイメージは、リポジトリのルートにある `/media/shared` フォルダーに格納します。

次のイメージ ファイルの種類がサポートされています: *.png"、*.gif"、*.jpeg"、*.jpg"、*.svg

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
