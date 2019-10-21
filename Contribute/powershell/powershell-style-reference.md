---
title: コマンドレット リファレンスの記述に関する具体的なガイダンス
description: この記事では、PowerShell コード サンプルの書式設定に関する具体的な規則について説明します。 これは、例が含まれる概念記事や、コマンドレット リファレンスに適用されます。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: sdwheeler
ms.author: sewhee
ms.date: 10/09/2019
ms.openlocfilehash: 793a3c02ae0edf192416ae514585d5161e8c1f98
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72290290"
---
# <a name="updating-reference-articles"></a>リファレンス記事の更新

コマンドレットのリファレンス記事には、特定の構造があります。 この構造は、[PlatyPS][] によって定義されています。
PlatyPS は、PowerShell モジュール用のコマンドレット ヘルプを生成するために使用されているツールです。 PlatyPS では、コマンドレット用の基になるマークダウン ファイルが作成されます。 マークダウン ファイルを編集した後、PlatyPS を使用して、`Get-Help` コマンドレットによって使用される MAML ヘルプ ファイルを作成します。

PlatyPS には、コード内に記述されるコマンドレット リファレンス用のハードコーディングされたスキーマが含まれます。 [platyPS.schema.md][] ドキュメントでは、この構造が記述されています。 スキーマ違反があると、投稿を受け入れる前に修正する必要があるビルド エラーが発生します。

## <a name="general-guidelines"></a>一般的なガイドライン

- ヘッダー構造は削除しないでください。 PlatyPS では、特定のヘッダーのセットが想定されています。
- **Input type** ヘッダーと **Output type** ヘッダーでは、型が必要です。 コマンドレットが入力を受け取らない場合、または値を返さない場合は、値 "None" を使用します。
- フェンスされたコード ブロックは、[Examples](#format-for-examples) セクションでのみ許可されています。
- インライン コード スパンは、どのパラグラフでも使用できます。

## <a name="formatting-about_-files"></a>About_ ファイルの書式設定

`About_*` ファイルは、PlatyPS ではなく、[Pandoc][] によって処理されるようになっています。 `About_*` ファイルは、PowerShell のすべてのバージョンおよび発行ツールとの間で最善の互換性が得られるように書式設定されます。
リポジトリ メンテナンス ツールでチェックインせずに、`about_*` ファイルの書式設定を変更しないでください。

基本的な書式設定に関するガイドライン:

- 行は 80 文字に制限されます
- コード ブロック、ブロック引用、およびテーブルは、Pandoc による変換の間にスペース 4 つ分インデントされるため、文字数は 76 文字に制限されます
- テーブルは 76 文字以内に収める必要があります
  - 複数行にまたがるセルの内容は手動で折り返します
  - 各行で開始と終了の `|` 文字を使用します
  - [about_Comparison_Operators][about-example] で実際の例を参照してください
- Pandoc の特殊文字 `\`、`$`、`` ` ``、`<` を使用するとき
  - ヘッダー内 - これらの文字は、先頭に `\` 文字を使用してエスケープする必要があります
  - パラグラフ内 - これらの文字は、コード スパン内に配置する必要があります。 次に例を示します。

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

## <a name="format-for-examples"></a>例の書式設定

PlatyPS スキーマでは、**EXAMPLES** ヘッダーは H2 ヘッダーであり、各例は H3 ヘッダーです。

例の内部では、コード ブロックをパラグラフで区切ることは、スキーマで許可されていません。 有効なスキーマは次のとおりです。

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

各例に番号を指定し、簡単なタイトルを追加します。

次に例を示します。

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This example gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```
~~~


[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/PowerShell/PowerShell-Docs/issues/1806
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/6/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org