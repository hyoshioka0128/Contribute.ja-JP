---
title: ドキュメントにコードを追加する方法
description: コード要素およびスニペットを記事に追加して、docs.microsoft.com に公開する方法について説明します。
author: tdykstra
ms.author: tdykstra
ms.date: 03/03/2020
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: b33333a49df11f0234193ca84fc2c3accdb6894d
ms.sourcegitcommit: f1535713b66ff9b840f1138583746bc2bf182b4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91953652"
---
# <a name="how-to-include-code-in-docs"></a>ドキュメントにコードを追加する方法

docs.microsoft.com に公開された記事にコードを追加する方法は、次のように複数あります。

* 1 行の中にある個々の要素 (単語)。

  `code` スタイルの例を次に示します。

  テキスト内の近くのコード ブロックで名前付きパラメーターと変数を参照する場合は、コード形式を使用します。 コード形式は、プロパティ、メソッド、クラス、および言語キーワードにも使用できます。 詳細については、この記事で後述する「[コード要素](#code-elements)」を参照してください。

* 記事の Markdown ファイル内のコード ブロック。

  ```markdown
      ```csharp
      public static void Log(string message)
      {
          _logger.LogInformation(message);
      }
      ```
  ```

  コード ファイルへの参照によるコード表示が実用的でない場合は、インライン コード ブロックを使用します。 詳細については、この記事で後述する「[コード ブロック](#inline-code-blocks)」を参照してください。

* ローカル リポジトリ内のコード ファイルへの参照によるコード ブロック。

  ```markdown
  :::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
  ```

  詳細については、この記事で後述する「[リポジトリ内のスニペットの参照](#in-repo-snippet-references)」を参照してください。

* 別のリポジトリのコード ファイルへの参照によるコード ブロック。

  ```markdown
  :::code language="csharp" source="~/samples-durable-functions/samples/csx/shared/Location.csx" highlight="2,5":::
  ```
  
  詳細については、この記事で後述する「[リポジトリの外にあるスニペットの参照](#out-of-repo-snippet-references)」を参照してください。
  
* ブラウザーでユーザーがコードを実行できるコード ブロック。

   ```markdown
  :::code source="PowerShell.ps1" interactive="cloudshell-powershell":::
  ```

  詳細については、この記事で後述する「[対話型コード スニペット](#interactive-code-snippets)」を参照してください。

コードを追加するためにこれらの各方法で使用する Markdown の説明に加えて、この記事では、[すべてのコード ブロックに対する一般的なガイダンス](#code-blocks)をいくつか紹介します。

## <a name="code-elements"></a>コード要素

「コード要素」は、プログラミング言語のキーワード、クラス名、プロパティ名などです。 どれをコードとして見なすかが、常に明確というわけではありません。 たとえば、NuGet パッケージの名前は、コードとして処理されます。 明確でない場合は、[テキスト書式設定のガイドライン](text-formatting-guidelines.md)に関するページをご覧ください。

### <a name="inline-code-style"></a>インライン コード スタイル

記事のテキストにコード要素を追加するには、コード スタイルを示すバッククォート (\`) でテキストを囲みます。
インライン コード スタイルでは、トリプル バッククォート形式を使用しないでください。

|Markdown |表示 |
|---------|---------|
|既定では、Entity Framework は、\`Id\` または \`ClassnameID\` という名前のプロパティを主キーとして解釈します。|既定では、Entity Framework は、`Id` または `ClassnameID` という名前のプロパティを主キーとして解釈します。|

記事がローカライズされる (他の言語に翻訳される) 場合、コードのテキスト スタイルは翻訳されないままになります。 コード スタイルを使用せずにローカライズしないようにするには、「[Non-localized strings](markdown-reference.md#non-localized-strings)」 (ローカライズしない文字列) を参照してください。

### <a name="bold-style"></a>太字スタイル

一部の古いスタイル ガイドでは、インライン コードには太字を指定しています。 太字は、コード スタイルが目立ってしまい読みやすさが損なわれる場合の選択肢になります。 たとえば、大部分がコード要素の Markdown テーブルの場合、すべてにコード スタイルを設定すると、非常に見にくくなる場合があります。 太字スタイルの使用を選択した場合は、[ローカライズしない文字列の構文](markdown-reference.md#non-localized-strings)を使用して、コードがローカライズされないことを確認します。

### <a name="links"></a>リンク

参考資料へのリンクは、コンテキストによってはコード形式よりも役に立つ場合があります。 リンクを使用する場合は、リンク テキストにコード形式を適用しないでください。 リンクをコードとしてスタイル設定すると、テキストがリンクであるという事実が分かりにくくなります。

リンクを使用し、同じコンテキスト内で後で同じ要素を参照する場合は、後続のインスタンスをリンクではなくコード形式にします。

### <a name="placeholders"></a>プレースホルダー

表示されているコードのセクションをユーザーが独自の値で置換できるようにするには、山かっこまたは中かっこで囲んだプレースホルダー テキストを使用します。 たとえば、`az group delete -n <ResourceGroupName>` のようにします。 実際の値で置換するときに、山かっこまたは中かっこを削除する必要があることを説明します。

## <a name="code-blocks"></a>コード ブロック

ドキュメントにコードを含める構文は、コードの配置場所によって異なります。

* [記事のマークダウン ファイル内にある](#inline-code-blocks)
* [同じリポジトリのコード ファイル内にある](#in-repo-snippet-references)
* [異なるリポジトリのコード ファイル内にある](#out-of-repo-snippet-references)

3 種類のコード ブロックすべてに適用されるガイドラインを次に示します。

* [コード検証を自動化する。](#code-validation)
* [コードの主な行を強調表示する。](#highlighting)
* [水平スクロール バーを避ける。](#horizontal-scroll-bars)

### <a name="screenshots"></a>スクリーンショット

前のセクションに示したメソッドはすべて、使用可能なコード ブロックになります。

* コピーして貼り付けることができます。
* 検索エンジンによってインデックスが作成されます。
* スクリーン リーダーからアクセスできます。

これらは、記事にコードを含める方法として IDE スクリーンショットが推奨されない理由のほんの一部です。 コードに IDE スクリーンショットを使用するのは、IntelliSense のように IDE 自体について何かを示す場合のみです。 色付けや強調表示を示すためだけにスクリーンショットを使用しないでください。

### <a name="code-validation"></a>コードの検証

一部のリポジトリには、すべてのサンプル コードを自動的にコンパイルしてエラーをチェックする処理が実装されています。 これは .NET リポジトリによって行われます。 詳細については、.NET リポジトリの「[Contributing](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)」 (寄稿) をご覧ください。

別のリポジトリのコード ブロックを挿入する場合は、コードで使用するライブラリの新しいバージョンが出荷されたときに、挿入したコードが壊れたり、古くなったりしないように、コードの保守戦略について所有者と協力します。

### <a name="highlighting"></a>強調表示

コンテキストを提供するために、通常、スニペットには必須コード以外も含まれます。 次の例に示すように、スニペット内で注目している主要な行を強調すると、読みやすくなります。

![強調表示されたコードを示した例](media/code-in-docs/highlighted-code.png)

記事のマークダウン ファイルにコードを追加する場合は、コードを強調表示できません。 コード ファイルへの参照によって追加されたコード スニペットに対してのみ、強調表示が有効です。

### <a name="horizontal-scroll-bars"></a>水平スクロール バー

水平スクロール バーを避けるために、長い行は分割します。 コード ブロック上のスクロール バーは、コードを読みにくくします。 比較的長いコード ブロックでは特に問題になります。このようなブロックでは、スクロール バーと読みたい行を同時に表示できない場合があるためです。

コード ブロックの水平スクロール バーを最小限に抑えるには、85 文字を超えるコード行を分割することをお勧めします。 ただし、スクロール バーの有無は、読みやすさの唯一の条件ではないことに注意してください。 85 文字より前で行を改行すると、読みやすさやコピーおよび貼り付けの利便性が損なわれる場合は、85 文字を超えてもかまいません。

## <a name="inline-code-blocks"></a>インライン コード ブロック

コード ファイルへの参照によるコード表示が実用的でない場合にのみ、インライン コード ブロックを使用します。 一般に、インライン コードは完全なプロジェクトに含まれるコード ファイルと比較すると、テストして最新の状態に保つことが困難です。  また、インライン コードでは、開発者がコードを理解して使用するのに役立つコンテキストを省略する場合があります。 これらの考慮事項は主にプログラミング言語に適用されます。 インライン コード ブロックは、出力と入力 (JSON など)、クエリ言語 (SQL など)、スクリプト言語 (PowerShell など) にも使用できます。
  
記事のファイルでテキストのセクションを示す方法は 2 つあります。トリプル バックフォード (\`\`\`) で *フェンス設定* するか、またはインデント設定します。 言語を指定できるので、フェンス設定の使用をお勧めします。 インデントは使用しないようにします。非常に誤解を招きやすく、他の作成者が、記事を編集する必要がある場合に作成時の意図を理解するのが難しくなる可能性があります。

次の例に示すように、言語インジケーターは、開始を示すトリプル バックフォードの直後に配置されます。

マークダウン:

```markdown
    ```json
    {
        "aggregator": {
            "batchSize": 1000,
            "flushTimeout": "00:00:30"
        }
    }
    ```
```

表示:

```json
{
    "aggregator": {
        "batchSize": 1000,
        "flushTimeout": "00:00:30"
    }
}
```

言語インジケーターとして使用できる値の詳細については、「[Language names and aliases](http://highlightjs.readthedocs.io/en/latest/css-classes-reference.html#language-names-and-aliases)」 (言語名およびエイリアス) をご覧ください。

サポートされていないトリプル バッククォート (\`\`\`) の後に言語または環境の単語を使用すると、表示されるページのコード セクションのタイトル バーにその単語が表示されます。 可能な場合は、インライン コード ブロックで言語または環境インジケーターを使用します。

> [!NOTE]
> Word 文書からコードをコピーして貼り付ける場合は、コード内に無効な "中かっこ" がないことを確認してください (たとえば、`“` と `’`)。 ある場合は、通常の引用符 (`'` と `"`) に戻します。 または、Docs Authoring Pack の[スマート クォート置換機能](docs-authoring/smart-quote-replacement.md)を利用します。

## <a name="in-repo-snippet-references"></a>リポジトリ内のスニペットの参照

ドキュメントにプログラミング言語のコード スニペットを追加するお勧めの方法は、コード ファイルの参照です。 この方法を使用すると、コード行を強調表示する機能を利用でき、GitHub のより広範囲のスニペットが利用可能になり、開発者が使用できます。 手動で、または [docs.microsoft.com Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) を利用して Visual Studio Code 内で、トリプル コロン形式 (:\:\:) を使用して、コードを追加することができます。

1. Visual Studio Code で、<kbd>Alt + M</kbd> キーまたは <kbd>Option + M</kbd> キーをクリックし、[スニペット] を選択します。
2. [スニペット] を選択すると、[Full Search]\(完全な検索\)、[Scoped Search]\(範囲検索\)、または [Cross-Repository Reference]\(リポジトリ間の参照\) の選択を求めるメッセージが表示されます。 ローカルで検索するには、[Full Search]\(完全な検索\) を選択します。
3. 検索用語を入力してファイルを検索します。 ファイルが見つかったら、そのファイルを選択します。
4. 次に、スニペットに含めるコードの行を決定するオプションを選択します。 オプションは次のとおりです: **[ID]** 、 **[範囲]** 、および **[なし]** 。
5. 手順 4 で行った選択に基づき、必要に応じて値を指定します。

コード ファイル全体を表示します。

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs":::
```

行番号を指定して、コード ファイルの一部を表示します。

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

スニペット名を指定して、コード ファイルの一部を表示します。

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" id="snippet_Create":::
```

次のセクションでは、これらの例について説明しています。

* [コード ファイルへの相対パスを使用する](#path-to-code-file)
* [選択した行番号のみを含める](#selected-line-numbers)
* [名前付きのスニペットを参照する](#named-snippet)
* [選択した行を強調表示する](#highlighting-selected-lines)

詳細については、この記事で後述する「[スニペットの構文リファレンス](#snippet-syntax-reference)」を参照してください。

### <a name="path-to-code-file"></a>コード ファイルへのパス

例:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

例は、ASP.NET ドキュメント リポジトリの [aspnetcore/data/ef-mvc/crud.md](https://github.com/aspnet/Docs/blob/master/aspnetcore/data/ef-mvc/crud.md) 記事のファイルです。 コード ファイルが、同じリポジトリ内の [aspnetcore/data/ef-mvc/intro/samples/cu/Controllers/StudentsController.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/data/ef-mvc/intro/samples/cu/Controllers/StudentsController.cs) への相対パスによって参照されています。

### <a name="selected-line-numbers"></a>選択した行番号

例:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26":::
```

この例では、 *StudentController.cs* コード ファイルの行 2 から 24 までと行 26 のみが表示されます。

次のセクションで説明するように、行番号をハードコーディングするよりも名前付きのスニペットを使用してください。

### <a name="named-snippet"></a>名前付きのスニペット

例:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" id="snippet_Create":::
```

名前には文字とアンダースコアのみを使用します。

例では、コード ファイルの `snippet_Create` セクションを表示します。 この例のコード ファイルでは、C# コードのコメント内にスニペット タグがあります。

```cs
// code excluded from the snippet
// <snippet_Create>
// code included in the snippet
// </snippet_Create>
// code excluded from the snippet
```

可能な限り、行番号の指定ではなく、名前付きセクションを使用してください。 コード ファイルが、行番号の変更を伴う方法で変更されることは不可避なため、行番号の参照は脆弱です。
このような変更は、必ずしも通知されません。 最終的には、自分の記事に誤った行が表示され始め、変更が行われたという手がかりも得られません。

### <a name="highlighting-selected-lines"></a>選択した行を強調表示する

例:

```markdown
:::code language="csharp" source="intro/samples/cu/Controllers/StudentsController.cs" range="2-24,26" highlight="2,5":::
```

この例では、表示されているスニペットの冒頭から数えて、2 番目と 5 番目の行が強調表示されています  強調表示する行番号は、コード ファイルの先頭からカウントされません。 つまり、コード ファイルの行 3 から 6 までが強調表示されています。

## <a name="out-of-repo-snippet-references"></a>リポジトリの外にあるスニペットの参照

参照したいコード ファイルが別のリポジトリにある場合は、そのコード リポジトリを " *依存リポジトリ* " として設定します。 これを行う場合は、その名前を指定します。 その後、この名前は、コード参照の目的のために、フォルダー名のように機能します。

たとえば、ドキュメント リポジトリが *Azure/azure-docs* で、コード リポジトリが *Azure/azure-functions-durable-extension* であるとします。

*azure-docs* のルート フォルダーで、 *.openpublishing.publish.config.json* に次のセクションを追加します。

```json
    {
      "path_to_root": "samples-durable-functions",
      "url": "https://github.com/Azure/azure-functions-durable-extension",
      "branch": "master",
      "branch_mapping": {}
    },
```

これで、 *azure-docs* 内のフォルダーであるかのように *samples-durable-functions* を参照すると、実際には *azure-functions-durable-extension* リポジトリ内のルート フォルダーを参照するようになります。

手動で、または [docs.microsoft.com Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) を利用して Visual Studio Code 内で、トリプル コロン形式 (:\:\:) を使用して、コードを追加することができます。

1. Visual Studio Code で、<kbd>Alt + M</kbd> キーまたは <kbd>Option + M</kbd> キーをクリックし、[スニペット] を選択します。
2. [スニペット] を選択すると、[Full Search]\(完全な検索\)、[Scoped Search]\(範囲検索\)、または [Cross-Repository Reference]\(リポジトリ間の参照\) の選択を求めるメッセージが表示されます。 リポジトリ間で検索するには、[Cross-Repository Reference]\(リポジトリ間の参照\) を選択します。
3. *.openpublishing.publish.config.json* に含まれているリポジトリの中から選択できるようになります。 リポジトリを選択します。
4. 検索用語を入力してファイルを検索します。 ファイルが見つかったら、そのファイルを選択します。
5. 次に、スニペットに含めるコードの行を決定するオプションを選択します。 オプションは次のとおりです: **[ID]** 、 **[範囲]** 、および **[なし]** 。
6. 手順 5 で行った選択に基づき、値を指定します。

スニペット参照は次のようになります。

```markdown
:::code language="csharp" source="~/samples-durable-functions/samples/csx/shared/Location.csx" highlight="2,5":::
```

*azure-functions-durable-extension* リポジトリでは、このコード ファイルは *samples/csx/shared* フォルダー内にあります。 [前述](#highlighting-selected-lines)したように、強調表示する行番号は、ファイルの先頭ではなく、スニペットの先頭からの相対です。

> [!NOTE]
> 依存リポジトリに割り当てる名前はメイン リポジトリのルートからの相対ですが、チルダ (~) はドキュメント セットのルートを指します。 ドキュメント セットのルートは、 *.openpublishing.publish.config.json* の `build_source_folder` によって決定されます。 前の例のスニペットへのパスは、azure docs リポジトリ内で動作します。これは、`build_source_folder` がリポジトリのルート (`.`) を指すためです。 `build_source_folder` が `articles` の場合、パスは `~/samples-durable-functions` ではなく `~/../samples-durable-functions` で始まります。

## <a name="interactive-code-snippets"></a>対話型コード スニペット

### <a name="inline-interactive-code-blocks"></a>インライン対話型コード ブロック

以下の言語の場合、コード スニペットはブラウザー ウィンドウで実行可能にすることが可能です。

* Azure Cloud Shell
* Azure PowerShell Cloud Shell
* C# REPL

対話モードが有効になっている場合、表示されたコード ボックスは **[Try It]\(お試し\)** または **[実行]** ボタンを備えています。 次に例を示します。

```markdown
    ```azurepowershell-interactive
    New-AzResourceGroup -Name myResourceGroup -Location westeurope
    ```
```

次のように表示されます。

```azurepowershell-interactive
New-AzResourceGroup -Name myResourceGroup -Location westeurope
```

特定のコード ブロックに対してこの機能を有効にするには、特別な言語識別子を使用します。 利用可能なオプションは、次のとおりです。

* `azurepowershell-interactive` - 前の例にあるように、Azure PowerShell Cloud Shell を有効にする
* `azurecli-interactive` - Azure Cloud Shell を有効にする
* `csharp-interactive` - C# REPL を有効にする

Azure Cloud Shell および PowerShell Cloud Shell の場合、ユーザーは独自の Azure アカウントのみに対してコマンドを実行できます。

### <a name="code-snippets-included-by-reference"></a>参照により追加されるコード スニペット

参照で追加されたコード スニペットの対話モードを有効にできます。 以下に例を示します。

```markdown
:::code source="PowerShell.ps1" interactive="cloudshell-powershell":::
```

```markdown
:::code source="Bash.sh" interactive="cloudshell-bash":::
```

特定のコード ブロックに対してこの機能をオンにするには、`interactive` 属性を使用します。 使用可能な属性値は次のとおりです。

* `cloudshell-powershell` - 前の例にあるように、Azure PowerShell Cloud Shell を有効にする
* `cloudshell-bash` - Azure Cloud Shell を有効にする
* `try-dotnet` - .NET Interactive を有効にする
* `try-dotnet-class` - クラス スキャフォールディングを使用した .NET Interactive を有効にする
* `try-dotnet-method` - メソッド スキャフォールディングを使用した .NET Interactive を有効にする

Azure Cloud Shell および PowerShell Cloud Shell の場合、ユーザーは自分の Azure アカウントに対してのみコマンドを実行できます。

.NET Interactive のエクスペリエンスについて、コード ブロックの内容は、次の 3 つのスキャフォールディング エクスペリエンスのどれを選択するかによって異なります。

* " *スキャフォールディングなし* " (`try-dotnet`):コード ブロックによって、完全なプログラム テキストを表す必要があります。 たとえば、`dotnet new console` によって生成される *Program.cs* ファイルは有効です。 これらは、必要な `using` ディレクティブなど、小さなプログラム全体を表示する場合に最も役立ちます。 最上位レベルのステートメントは現時点ではサポートされていません。
* " *メソッド スキャフォールディング* " (`try-dotnet-method`):コード ブロックによって、コンソール アプリケーションの `Main` メソッドの内容を表す必要があります。 `dotnet new console` テンプレートによって追加された `using` ディレクティブを想定できます。 この設定は、1 つの機能を表す短いスニペットに最も役立ちます。
* " *クラス スキャフォールディング* " (`try-dotnet-class`):コード ブロックによって、プログラムのエントリ ポイントとして `Main` メソッドを持つクラスを表す必要があります。 これらは、クラスのメンバーがどのように対話するかを示すために使用できます。

## <a name="snippet-syntax-reference"></a>スニペットの構文リファレンス

構文:

```md
:::code language="<language>" source="<path>" <attribute>="<attribute-value>":::
```

> [!IMPORTANT]
> この構文は、ブロックの Markdown 拡張機能です。 これは、独自の行で使用する必要があります。

* `<language>` ( *省略可能* )
  * コード スニペットの言語。 詳細については、この記事で後述する「[サポートされている言語](#supported-languages)」を参照してください。

* `<path>` ( *必須* )
  * 参照するコード スニペット ファイルを示すファイル システムの相対パス。

* `<attribute>` および `<attribute-value>` (" *省略可能* ")

  ファイルからコードを取得する方法とその表示方法を指定するために併せて使用。

  * `range`:　`1,3-5` 行の範囲です。 この例には、1、3、4、5 行が含まれます。
  * `id`:`snippet_Create` コード ファイルから挿入する必要があるスニペットの ID です。 この値を範囲と共存させることはできません。
  * `highlight`:`2-4,6` 生成されたコード スニペットで強調表示する必要がある行の範囲や数です。 番号は、ファイルではなく、表示される行 (範囲または ID で指定) からの相対です。
  * `interactive`: `cloudshell-powershell`、`cloudshell-bash`、`try-dotnet`、`try-dotnet-class`、`try-dotnet-method` String 値では、有効にする対話機能の種類を決定します。
  * 言語別のコード スニペット ソース ファイルでのタグ名表現の詳細については、[DocFX ガイドライン](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)を参照してください。

## <a name="supported-languages"></a>サポートされている言語

[Docs Authoring Pack](how-to-write-docs-auth-pack.md) には、コード フェンス ブロックに使用できる言語識別子のステートメント入力候補と検証を提供する機能が含まれています。

### <a name="fenced-code-blocks"></a>フェンスされたコード ブロック

| 名前                           | 有効なエイリアス                                                                  |
|--------------------------------|--------------------------------------------------------------------------------|
| .NET Core CLI                  | `dotnetcli`                                                                    |
| 1C                             | `1c`                                                                           |
| ABNF                           | `abnf`                                                                         |
| アクセス ログ                    | `accesslog`                                                                    |
| Ada                            | `ada`                                                                          |
| ARM アセンブラー                  | `armasm`、`arm`                                                                |
| AVR アセンブラー                  | `avrasm`                                                                       |
| ActionScript                   | `actionscript`, `as`                                                           |
| Alan                           | `alan`、`i`                                                                    |
| AngelScript                    | `angelscript`, `asc`                                                           |
| ANTLR                          | `antlr`                                                                        |
| Apache                         | `apache`, `apacheconf`                                                         |
| AppleScript                    | `applescript`, `osascript`                                                     |
| アーケード                         | `arcade`                                                                       |
| AsciiDoc                       | `asciidoc`, `adoc`                                                             |
| AspectJ                        | `aspectj`                                                                      |
| ASPX                           | `aspx`                                                                         |
| ASP.NET (C#)                   | `aspx-csharp`                                                                  |
| ASP.NET (VB)                   | `aspx-vb`                                                                      |
| AutoHotkey                     | `autohotkey`                                                                   |
| AutoIt                         | `autoit`                                                                       |
| Awk                            | `awk`, `mawk`, `nawk`, `gawk`                                                  |
| Axapta                         | `axapta`                                                                       |
| AzCopy                         | `azcopy`                                                                       |
| Azure CLI                      | `azurecli`                                                                     |
| Azure CLI (対話型)        | `azurecli-interactive`                                                         |
| Azure PowerShell               | `azurepowershell`                                                              |
| Azure Powershell (対話型) | `azurepowershell-interactive`                                                  |
| Bash                           | `bash`, `sh`, `zsh`                                                            |
| Basic                          | `basic`                                                                        |
| BNF                            | `bnf`                                                                          |
| C                              | `c`                                                                            |
| C#                             | `csharp`、`cs`                                                                 |
| C# (対話型)               | `csharp-interactive`                                                           |
| C++                            | `cpp`, `c`, `cc`, `h`, `c++`, `h++`, `hpp`                                     |
| C++/CX                         | `cppcx`                                                                        |
| C++/WinRT                      | `cppwinrt`                                                                     |
| C/AL                           | `cal`                                                                          |
| Cache Object Script            | `cos`, `cls`                                                                   |
| CMake                          | `cmake`, `cmake.in`                                                            |
| Coq                            | `coq`                                                                          |
| CSP                            | `csp`                                                                          |
| CSS                            | `css`                                                                          |
| Cap'n Proto                    | `capnproto`, `capnp`                                                           |
| Clojure                        | `clojure`, `clj`                                                               |
| CoffeeScript                   | `coffeescript`, `coffee`, `cson`, `iced`                                       |
| Crmsh                          | `crmsh`, `crm`, `pcmk`                                                         |
| Crystal                        | `crystal`, `cr`                                                                |
| Cypher (Neo4j)                 | `cypher`                                                                       |
| D                              | `d`                                                                            |
| DAX Power BI                   | `dax`                                                                          |
| DNS ゾーン ファイル                  | `dns`, `zone`, `bind`                                                          |
| DOS                            | `dos`, `bat`, `cmd`                                                            |
| Dart                           | `dart`                                                                         |
| Delphi                         | `delphi`, `dpr`, `dfm`, `pas`, `pascal`, `freepascal`, `lazarus`, `lpr`, `lfm` |
| [Diff]                           | `diff`, `patch`                                                                |
| Django                         | `django`, `jinja`                                                              |
| Dockerfile                     | `dockerfile`、`docker`                                                         |
| dsconfig                       | `dsconfig`                                                                     |
| DTS (デバイス ツリー)              | `dts`                                                                          |
| Dust                           | `dust`, `dst`                                                                  |
| Dylan                          | `dylan`                                                                        |
| EBNF                           | `ebnf`                                                                         |
| Elixir                         | `elixir`                                                                       |
| Elm                            | `elm`                                                                          |
| Erlang                         | `erlang`, `erl`                                                                |
| Excel                          | `excel`, `xls`, `xlsx`                                                         |
| Extempore                      | `extempore`, `xtlang`, `xtm`                                                   |
| F#                             | `fsharp`, `fs`                                                                 |
| FIX                            | `fix`                                                                          |
| Fortran                        | `fortran`, `f90`, `f95`                                                        |
| G-Code                         | `gcode`, `nc`                                                                  |
| Gams                           | `gams`, `gms`                                                                  |
| GAUSS                          | `gauss`, `gss`                                                                 |
| GDScript                       | `godot`, `gdscript`                                                            |
| Gherkin                        | `gherkin`                                                                      |
| GN for Ninja                   | `gn`、`gni`                                                                    |
| Go                             | `go`, `golang`                                                                 |
| Golo                           | `golo`, `gololang`                                                             |
| Gradle                         | `gradle`                                                                       |
| Groovy                         | `groovy`                                                                       |
| HTML                           | `html`, `xhtml`                                                                |
| HTTP                           | `http`, `https`                                                                |
| Haml                           | `haml`                                                                         |
| ハンドルバー                     | `handlebars`, `hbs`, `html.hbs`, `html.handlebars`                             |
| Haskell                        | `haskell`, `hs`                                                                |
| Haxe                           | `haxe`, `hx`                                                                   |
| Hy                             | `hy`, `hylang`                                                                 |
| Ini                            | `ini`                                                                          |
| Inform7                        | `inform7`, `i7`                                                                |
| IRPF90                         | `irpf90`                                                                       |
| JSON                           | `json`                                                                         |
| Java                           | `java`, `jsp`                                                                  |
| JavaScript                     | `javascript`, `js`, `jsx`                                                      |
| Kotlin                         | `kotlin`、`kt`                                                                 |
| Kusto                          | `kusto`                                                                        |
| Leaf                           | `leaf`                                                                         |
| なげなわ                          | `lasso`, `ls`, `lassoscript`                                                   |
| 未満                           | `less`                                                                         |
| LDIF                           | `ldif`                                                                         |
| Lisp                           | `lisp`                                                                         |
| LiveCode Server                | `livecodeserver`                                                               |
| LiveScript                     | `livescript`, `ls`                                                             |
| Lua                            | `lua`                                                                          |
| メイクファイル                       | `makefile`, `mk`, `mak`                                                        |
| Markdown                       | `markdown`, `md`, `mkdown`, `mkd`                                              |
| Mathematica                    | `mathematica`, `mma`, `wl`                                                     |
| Matlab                         | `matlab`                                                                       |
| Maxima                         | `maxima`                                                                       |
| Maya Embedded Language         | `mel`                                                                          |
| Mercury                        | `mercury`                                                                      |
| mIRC スクリプト言語        | `mirc`, `mrc`                                                                  |
| Mizar                          | `mizar`                                                                        |
| Managed Object Format          | `mof`                                                                          |
| Mojolicious                    | `mojolicious`                                                                  |
| Monkey                         | `monkey`                                                                       |
| Moonscript                     | `moonscript`、`moon`                                                           |
| MS Graph (対話型)         | `msgraph-interactive`                                                          |
| N1QL                           | `n1ql`                                                                         |
| NSIS                           | `nsis`                                                                         |
| Nginx                          | `nginx`、`nginxconf`                                                           |
| Nimrod                         | `nimrod`, `nim`                                                                |
| Nix                            | `nix`                                                                          |
| OCaml                          | `ocaml`, `ml`                                                                  |
| Objective C                    | `objectivec`, `mm`, `objc`, `obj-c`                                            |
| OpenGL シェーディング言語        | `glsl`                                                                         |
| OpenSCAD                       | `openscad`, `scad`                                                             |
| Oracle ルール言語          | `ruleslanguage`                                                                |
| Oxygene                        | `oxygene`                                                                      |
| PF                             | `pf`, `pf.conf`                                                                |
| PHP                            | `php`, `php3`, `php4`, `php5`, `php6`                                          |
| Parser3                        | `parser3`                                                                      |
| Perl                           | `perl`, `pl`, `pm`                                                             |
| Plaintext 強調表示なし         | `plaintext`                                                                    |
| Pony                           | `pony`                                                                         |
| PostgreSQL & PL/pgSQL          | `pgsql`, `postgres`, `postgresql`                                              |
| PowerShell                     | `powershell`, `ps`                                                             |
| Powershell (対話型)       | `powershell-interactive`                                                       |
| 処理中                     | `processing`                                                                   |
| Prolog                         | `prolog`                                                                       |
| Properties                     | `properties`                                                                   |
| プロトコル バッファー               | `protobuf`                                                                     |
| Puppet                         | `puppet`, `pp`                                                                 |
| Python                         | `python`, `py`, `gyp`                                                          |
| Python プロファイラーの結果        | `profile`                                                                      |
| Q#                             | `qsharp`                                                                       |
| Q                              | `k`、`kdb`                                                                     |
| QML                            | `qml`                                                                          |
| R                              | `r`                                                                            |
| Razor CSHTML                   | `cshtml`, `razor`, `razor-cshtml`                                              |
| ReasonML                       | `reasonml`, `re`                                                               |
| RenderMan RIB                  | `rib`                                                                          |
| RenderMan RSL                  | `rsl`                                                                          |
| Roboconf                       | `graph`、`instances`                                                           |
| Robot Framework                | `robot`, `rf`                                                                  |
| RPM spec ファイル                 | `rpm-specfile`, `rpm`, `spec`, `rpm-spec`, `specfile`                          |
| Ruby                           | `ruby`, `rb`, `gemspec`, `podspec`, `thor`, `irb`                              |
| Rust                           | `rust`、`rs`                                                                   |
| SAS                            | `SAS`, `sas`                                                                   |
| SCSS                           | `scss`                                                                         |
| SQL                            | `sql`                                                                          |
| STEP パート 21                   | `p21`, `step`, `stp`                                                           |
| Scala                          | `scala`                                                                        |
| Scheme                         | `scheme`                                                                       |
| Scilab                         | `scilab`, `sci`                                                                |
| Shape Expressions              | `shexc`                                                                        |
| Shell                          | `shell`, `console`                                                             |
| Smali                          | `smali`                                                                        |
| Smalltalk                      | `smalltalk`, `st`                                                              |
| Solidity                       | `solidity`, `sol`                                                              |
| Stan                           | `stan`                                                                         |
| Stata                          | `stata`                                                                        |
| Structured Text                | `iecst`, `scl`, `stl`, `structured-text`                                       |
| スタイラス                         | `stylus`, `styl`                                                               |
| SubUnit                        | `subunit`                                                                      |
| Supercollider                  | `supercollider`, `sc`                                                          |
| Swift                          | `swift`                                                                        |
| Tcl                            | `tcl`, `tk`                                                                    |
| Terraform (HCL)                | `terraform`, `tf`, `hcl`                                                       |
| Test Anything Protocol         | `tap`                                                                          |
| TeX                            | `tex`                                                                          |
| Thrift                         | `thrift`                                                                       |
| TOML                           | `toml`                                                                         |
| TP                             | `tp`                                                                           |
| Twig                           | `twig`、`craftcms`                                                             |
| TypeScript                     | `typescript`, `ts`                                                             |
| VB.NET                         | `vbnet`, `vb`                                                                  |
| [VBScript]                       | `vbscript`, `vbs`                                                              |
| VHDL                           | `vhdl`                                                                         |
| Vala                           | `vala`                                                                         |
| Verilog                        | `verilog`, `v`                                                                 |
| Vim スクリプト                     | `vim`                                                                          |
| X++                            | `xpp`                                                                          |
| x86 アセンブリ                   | `x86asm`                                                                       |
| XL                             | `xl`, `tao`                                                                    |
| XQuery                         | `xquery`, `xpath`, `xq`                                                        |
| XAML                           | `xaml`                                                                         |
| XML                            | `xml`, `xhtml`, `rss`, `atom`, `xjb`, `xsd`, `xsl`, `plist`                    |
| YAML                           | `yml`, `yaml`                                                                  |
| Zephir                         | `zephir`, `zep`                                                                |

> [!TIP]
> Docs Authoring Pack の [開発言語の完了機能](docs-authoring/dev-lang-completion.md)では、複数のエイリアスが使用可能な場合、最初に有効なエイリアスが使用されます。

## <a name="next-steps"></a>次のステップ

コード以外のコンテンツの種類に対するテキストの書式設定の詳細については、「[Text formatting guidelines](text-formatting-guidelines.md)」 (テキストの書式設定に関するガイドライン) を参照してください。
