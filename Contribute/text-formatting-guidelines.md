---
title: テキストの書式設定に関するガイドライン
description: docs.microsoft.com サイトで公開する記事で、どのようなときに太字、斜体、コード、およびその他のテキストのスタイルを使用するかについて説明します。
author: tdykstra
ms.author: tdykstra
ms.date: 01/30/2020
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 7b6927918c81fdc41e3c3887f94339b225e2a6e6
ms.sourcegitcommit: dbc2c48194e29bfa0c88d33f50f94b9ee26be2da
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78336492"
---
# <a name="text-formatting-guidelines"></a>テキストの書式設定に関するガイドライン

テキスト要素の太字、斜体、およびコード スタイルは、一貫性を保って適切に使用することで、読みやすさを向上させ、誤解を避けることに役立ちます。

## <a name="bold"></a>太字

メニューの選択肢、ダイアログ ボックス名、入力フィールド名などの UI 要素には太字を使用します。

### <a name="examples"></a>例

* **正**:**ソリューション エクスプローラー**で、プロジェクト ノードを右クリックして、 **[追加]、[新しいアイテム]** の順に選択します。
* **誤**:ソリューション エクスプローラーで、プロジェクト ノードを右クリックして、[追加]、[新しいアイテム] の順に選択します。
* **誤**:"*ソリューション エクスプローラー*" で、プロジェクト ノードを右クリックして、" *[追加]、[新しいアイテム]* " の順に選択します。

## <a name="italics"></a>斜体

次の場合は、斜体を使用します。

* 定義または説明で新しい用語を使用する。
* ファイル名、フォルダー名、パス。
* ユーザー入力。

### <a name="examples"></a>例

* **正**:App Service では、アプリは "*App Service プラン*" で実行されます。 App Service プランでは、Web アプリで実行するための一連のコンピューティング リソースを定義します。
* **誤**:App Service では、アプリは "App Service プラン" で実行されます。 App Service プランでは、Web アプリで実行するための一連のコンピューティング リソースを定義します。
* **正**:"*HttpTriggerCSharp.cs*" のコードを次のコードに置き換えます。
* **誤**:`HttpTriggerCSharp.cs` のコードを次のコードに置き換えます。
* **正**: **[名前]** に "*ContosoUniversity*" と入力し、 **[追加]** を選択します。
* **誤**: **[名前]** に "ContosoUniversity" と入力し、 **[追加]** を選択します。

## <a name="code-style"></a>コード スタイル

次の場合は、コード スタイルを使用します。

* メソッド名、プロパティ名、言語キーワードなどのコード要素。
* SQL コマンド
* NuGet パッケージ名
* コマンド ライン コマンド
* データベース テーブル名と列名
* ローカライズすべきではないリソース名 (仮想マシン名など)
* クリック可能にしない URL

**理由** 古いスタイル ガイドでは、これらのテキスト要素の多くに太字が指定されています。 しかし、ほとんどの記事はローカライズされるため、コード スタイルを使用して、テキストのその部分を翻訳せずにそのままにしておくように翻訳者に指示します。

コード スタイルには、"*インライン*" (\` で囲む)、または複数の行にまたがる "*フェンスされた*" コード ブロック (\`\`\` で囲む) を使用できます。 長いコード スニペットとパスは、フェンスされたコード ブロック内に配置します。

### <a name="examples-using-inline-styles"></a>インライン スタイルの使用例

* **正**:既定では、Entity Framework は、`Id` または `ClassnameID` という名前のプロパティを主キーとして解釈します。
* **誤**:既定では、Entity Framework は、*Id* または *ClassnameID* という名前のプロパティを主キーとして解釈します。
* **正**:`Microsoft.EntityFrameworkCore` パッケージは、EF Core のランタイム サポートを提供します。
* **誤**:"*Microsoft.EntityFrameworkCore*" パッケージは、EF Core のランタイム サポートを提供します。

### <a name="examples-of-fenced-code-blocks"></a>フェンスされたコード ブロックの例

* **正**:次のコードのように、`IQueryable` を変更しただけのステートメントでは、データベースにコマンドは送信されません。

  ```markdown
      ```csharp
      var students = context.Students.Where(s => s.LastName == "Davolio")
      ```
  ```

* **誤**:**var students = context.Students.Where(s => s.LastName == "Davolio")** のように、**IQueryable**を変更しただけのステートメントでは、データベースにコマンドは送信されません。

* **正**:たとえば、`C:\Scripts` ディレクトリで `Get-ServiceLog.ps1` スクリプトを実行するには、次を入力します。

  ```markdown
      ```powershell
      C:\Scripts\Get-ServiceLog.ps1
      ```
  ```

* **誤**:たとえば、**C:\Scripts** ディレクトリで **Get-ServiceLog.ps1** スクリプトを実行するには、"C:\Scripts\Get-ServiceLog.ps1" と入力します。

* **すべての**フェンスされたコード ブロックには、承認された言語タグが必要です。 サポートされる言語タグの一覧については、[docs にコードを含める方法](./code-in-docs.md#supported-languages)に関するページをご覧ください。

## <a name="headings-and-link-text"></a>見出しとリンク テキスト

斜体、太字、またはコードなどのインライン スタイルは、見出しやハイパーリンク テキストに適用しないでください。

**理由**

ユーザーは、標準のハイパーリンク テキストを頼りに、テキスト要素をクリック可能なリンクとして識別します。 たとえば、リンクをコードとしてスタイル設定すると、テキストがリンクであるという事実が分かりにくくなります。 見出しには独自のスタイルがあり、異なるスタイルを混在させると、見た目が悪くなります。

### <a name="examples"></a>例

* **正**:"*function.json*" ファイルは、NuGet パッケージ ([Microsoft.NET.Sdk.Functions](http://www.nuget.org/packages/Microsoft.NET.Sdk.Functions)) によって生成されます。
* **誤**:"*function.json*" ファイルは、NuGet パッケージ ([`Microsoft.NET.Sdk.Functions`](http://www.nuget.org/packages/Microsoft.NET.Sdk.Functions)) によって生成されます。

* **正**:

  ```markdown
  ### The Microsoft.NET.Sdk.Functions package
  ```

* **誤**:

  ```markdown
  ### The `Microsoft.NET.Sdk.Functions` package
  ```

## <a name="keys-and-keyboard-shortcuts"></a>キーおよびキーボード ショートカット

キーまたはキーの組み合わせを参照する場合、次の規約に従います。

* キー名の最初の文字を大文字にする。
* 斜体、太字、コードなどのインライン スタイルを適用しない。
* 同時に押すキーを結合するには、"+" を使用する。

### <a name="examples"></a>例

* **正**:Alt + Ctrl + S キーを選択します。
* **誤**:**ALT + CTRL + S** キーを押します。
* **誤**:`ALT+CTRL+S`を押します。

詳細については、「[UI を使用した対話式操作の記述](https://styleguides.azurewebsites.net/StyleGuide/Read?id=2700&topicid=26472)」を参照してください。

## <a name="exceptions"></a>例外

スタイル ガイドラインは、厳格なルールではありません。 読みやすさが損なわれる場合は、別のスタイルを使用してください。 たとえば、大部分がコード要素の HTML テーブルの場合、すべてにコード スタイルを設定すると、非常に見にくくなる場合があります。 このような場合、太字のスタイルを選択することもできます。

通常はコードを呼び出す代替テキスト スタイルを選択する場合、記事のローカライズ バージョンでそのテキストを翻訳できることを確認してください。 コードは、翻訳を自動的に防止する唯一のスタイルです。 コード スタイルを使用しないでローカライズを防止する必要があるシナリオについては、「[ローカライズしない文字列](markdown-reference.md#non-localized-strings)」を参照してください。
