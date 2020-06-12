---
title: .NET ドキュメント リポジトリに協力する
description: この記事では、.NET ドキュメントを構成するレポジトリ内の記事やコード サンプルに協力する過程について説明しています。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 05/14/2020
ms.openlocfilehash: c4382a66035a10debb2a0aa05f61c549a3f97ee6
ms.sourcegitcommit: 300ce72ffc8596213e82ae511b1b314c850841c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83404132"
---
# <a name="learn-how-to-contribute-to-the-net-docs-repositories"></a>.NET ドキュメント リポジトリに協力する方法について説明します

.NET ドキュメントへの協力にご関心をお寄せいただきありがとうございます。

このドキュメントでは、[.NET ドキュメント サイト](https://docs.microsoft.com/dotnet)に掲載される記事やコード サンプルに協力する過程について取り上げています。 協力には誤植の修正のような単純なものから、新しい記事のような入り組んだものまであります。

.NET ドキュメント サイトは複数のリポジトリから構築されています。

- [.NET の概念に関する記事](https://github.com/dotnet/docs)
- [コードのサンプルとスニペット](https://github.com/dotnet/samples)
- [.NET Standard、.NET Core、.NET Framework API リファレンス](https://github.com/dotnet/dotnet-api-docs)
- [.NET Compiler Platform SDK リファレンス](https://github.com/dotnet/roslyn-api-docs)
- [ML.NET API リファレンス](https://github.com/dotnet/ml-api-docs)

以上のリポジトリの問題は [dotnet/docs](https://github.com/dotnet/docs/issues) リポジトリで追跡されます。

## <a name="guidelines-for-contributions"></a>投稿のガイドライン

ドキュメントに対するコミュニティの投稿に感謝します。 .NET ドキュメントを共同作成する際に留意する必要がある適用規則のいくつかを次の一覧に示します。

- Microsoft が予期していない大量の pull request を**送信しないでください**。 Issue を提出してディスカッションを開始していただければ、長い時間が費やされる前に Microsoft はその目的に同意することができます。
- 以下に示す手順と[ボイスおよびトーン](dotnet-voice-tone.md)のガイドラインに**従ってください**。
- ご自分の作業の出発点として**テンプレート ファイル**を[使用してください](dotnet-style-guide.md)。
- 記事で作業する前に、使用するフォーク上に独立したブランチを**作成します**。
- [GitHub フロー ワークフロー](https://guides.github.com/introduction/flow/)に**従います**。
- ご自分の共同作成について頻繁にブログ投稿およびツイート (または同類の作業) を**行います**。

このようなガイドラインに従うことにより、ご自分にとっても Microsoft にとってより望ましいエクスペリエンスが確保されます。

## <a name="make-a-contribution-to-net-docs"></a>.NET ドキュメントに対する共同作成

**手順 1:** 小さな変更の場合はこの手順はスキップします。 新しいコンテンツの作成または既存のコンテンツの徹底的な改訂に関心がある場合は、ご自分が行いたい内容を説明する [Issue](https://github.com/dotnet/docs/issues) を開示してください。

**docs** フォルダー内のコンテンツはセクションに編成され、これらのこのセクションは目次 (TOC) に反映されます。 TOC 内でトピックが配置される場所を定義します。 ご自分の提案に対するフィードバックを取得します。

または

コミュニティへの投稿が歓迎されている既存の Issue から選択することもできます。 「[Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35)」 (.NET コミュニティ共同作成者用のプロジェクト) に、コミュニティ共同作成者が利用できる Issue が多数一覧されています。 ご自分の関心とコミットメントのレベルに応じて、次に示すカテゴリに属する Issue の中から該当するものを選択することができます。

- **メンテナンス**。 このカテゴリには、壊れたリンクや誤ったリンクの修正、不足しているコード例の追加、限定されたコンテンツ Issue への対処など、比較的シンプルな共同作成が含まれています。 場合によって、これらの Issue は多数のファイルにかかわっている場合があります。 そのような場合は、始める前に、作業対象とするものを Microsoft に知らせてください。 Issue に対してコメントを追加することで、ご自分がその Issue で作業していることを Microsoft に伝えてください。

- **コンテンツの更新**。 発生するドキュメント セットは膨大であるため、コンテンツはすぐに古くなり、改訂が必要になります。 さらに、コンテンツによってはさまざまな理由で、複製されていたり、さらには正副 3 部目が複製されていたりします。 コンテンツの更新では、個々のトピックが機能領域において現在のコンテンツであるか、それとも改訂対象のコンテンツであるかを確認する必要があります。これにより、重複をなくし、すべての一意のコンテンツがよりコンパクトなドキュメント セットで確実に保持されるようにすることができます。

- **新しいコンテンツの作成**。 独自のトピックを作成することに関心がある場合は、これらの Issue を参照してください。Microsoft がドキュメントセットへの追加を望んでいることを自身で認めているトピックが一覧されています。 ただし、トピックに対して作業を開始する前に Microsoft にその旨をお知らせください。 ここに一覧されていないトピックの作成に関心がある場合は、Issue を開示してください。

また、[開示状態の Issue ](https://github.com/dotnet/docs/issues)の一覧とボランティアを参照して、関心がある Issue で作業することもできます。 Microsoft では、[up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) ラベルを使用して、コミュニティ共同作成用として識別された Issue にタグ付けしています。 通常これらで必要となるのは最小限のコンテキストであり、初めての Issue として最適です。 Microsoft はコミュニティ内の経験を積んでいる共同作成者に対し、関心を持てる Issue がないか確認するように奨励しています。 関心のある Issue が見つかったら、それが開示されているかどうかをたずねるコメントを追加します。

作業するタスクを選択したら、[ファースト ステップ](../get-started-setup-github.md) ガイドに従って、GitHub アカウントを作成し、使用する環境を設定します。

**手順 2:** `/dotnet/docs`、`dotnet/samples`、`dotnet/dotnet-api-docs`、`dotnet/roslyn-api-docs`、または `dotnet/ml-api-docs` リポジトリを必要に応じてフォークし、ご自分の変更のためにブランチを作成します。

小さい変更の場合は、共同作成者ガイドの[ホーム ページ](../index.md#quick-edits-to-existing-documents)上で "GitHub での編集の手順" を参照してください。

**手順 3:** この新しいブランチに対して変更を加えます。

それが新しいトピックである場合は、ご自分の出発点としてこの[テンプレート ファイル](dotnet-style-guide.md)を使用してください。 これには、文書作成のガイドラインに加えて、各記事で必要となるメタデータ (作成者情報など) に関する説明が含まれています。

手順 1 で決定したご自分の記事の TOC での場所に対応するフォルダーに移動します。 そのフォルダーには、そのセクションに属するすべての記事の Markdown ファイルが格納されています。 必要に応じて、ご自分のコンテンツのファイルを配置するフォルダーを新たに作成します。 そのセクションのメイン記事は、*index.md* と呼ばれます。

イメージなどの静的なリソースについては、ご自分の記事が格納されているフォルダー内に **media** というサブフォルダーを作成します (それがまだ作成されていない場合)。 **media** フォルダー内に、記事の名前を使用してサブフォルダーを作成します (ただし、インデックス ファイルは除く)。 

**コード スニペット**については、ご自分の記事が格納されているフォルダー内に **snippets** というサブフォルダーを作成します (それがまだ作成されていない場合)。  **snippets** フォルダー内に、記事の名前を使用してサブフォルダーを作成します。 ほとんどの場合、3 つの主要な .NET 言語 (C#、F#、Visual Basic) すべてに対してコード スニペットを用意することになります。 その場合は、3 つのプロジェクトそれぞれに対して **csharp**、**fsharp**、**vb** という名前のサブフォルダーを作成します。 わかりやすくするために、C# ガイド、F# ガイド、Visual Basic ガイドでは、プロジェクトに **snippets** フォルダーを使用してください。 これらの領域には、通常、1 つの言語のスニペットがあります。 コード スニペットは、記事で説明されている概念を示すコードに注目した小さなサンプルです。 ダウンロードと探索を目的とした大規模なプログラムは、[dotnet/samples](https://github.com/dotnet/samples) リポジトリに配置する必要があります。 完全なサンプルについては、[サンプルの共同作成](#contributing-to-samples)に関するセクションを参照してください。

適切な Markdown 構文に必ず従ってください。 一般的な例については、[テンプレートと Markdown に関する簡易参照ガイド](dotnet-style-guide.md)を参照してください。

## <a name="example-structure"></a>構造の例

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png
          /snippets
            /porting-overview
              /csharp
                porting.csproj
                porting-overview.cs
                Program.cs
              /fsharp
                porting.fsproj
                porting-overview.fs
                Program.fs
               /vb
                porting.vbproj
                porting-overview.vb
                Program.vb

上記の構造には、1 つのイメージ (*portability_report.png*) と、*porting-overview.md* の記事に含まれている**コード スニペット**を含む、3 つのコード プロジェクトが含まれています。 受け入れられた代替構造体には、そのフォルダー内のすべての記事のすべてのスニペットを含む言語ごとに 1 つのプロジェクトが含まれています。 この代替は、言語の構文を示す非常に小さなスニペットであるため、言語リファレンスの分野で使用されています。 他の領域では推奨されません。

歴史的な理由により、含まれているスニペットの多くは、*dotnet/docs* リポジトリの */samples* フォルダーに格納されています。 記事に大きな変更を加える場合は、それらのスニペットを新しい構造に移動する必要があります。 小さな変更ではスニペットを移動しないでください。

**手順 4:** ご利用のブランチからマスター ブランチに Pull Request (PR) を送信します。

> [!IMPORTANT]
> この時点で、[コメント オートメーション](../how-to-write-workflows-major.md#review-and-sign-off)機能は、すべての .NET ドキュメント リポジトリで使用できません。 この PR は .NET ドキュメント チームのメンバーによって確認およびマージされます。

各 PR では、通常、Issue を 1 つずつ取り扱う必要があります。 PR により、1 つまたは複数のファイルを変更することができます。 異なるそれぞれのファイル上で複数の修正に対処する場合、個別の PR が推奨されます。 Markdown の更新だけでなくサンプルの作成も行う場合は、サンプルに対して別個の PR を作成することが必要になります。

ご自分の PR によって既存の Issue を修正する場合は、コミット メッセージまたは PR 記述に `Fixes #Issue_Number` キーワードを追加します。 これにより、その Issue は PR がマージされると、自動的に終了されます。 詳細については、[コミット メッセージを介した Issue の終了](https://help.github.com/articles/closing-issues-via-commit-messages/) に関するページを参照してください。

.NET チームは送られてきた PR のレビューを行い、必要な更新/変更が他にも存在するために承認できない場合は、その旨をお知らせします。

**手順 5:** チームでディスカッションしたとおりに、ご自分のブランチに対して必要な更新を行います。

フィードバックが適用され、ご自分の変更が承認されると、その PR は Maintainer によってマスター ブランチにマージされます。

Microsoft によって定期的にすべてのコミットがマスター ブランチからライブ ブランチにプッシュされるので、 https://docs.microsoft.com/dotnet/ でご自分の共同作成をライブで確認できるようになります。 通常、Microsoft は営業日には毎日発行しています。 メンテナンス アクティビティにより発行が数日遅れる場合があります。

## <a name="contributing-to-samples"></a>サンプルに対する共同作成

[dotnet/samples](https://github.com/dotnet/samples) リポジトリには、.NET ドキュメントのいずれかのトピックに属するすべてのサンプル コードが含まれています。 サブフォルダー内に整理されるプロジェクトが数種類あります。 これらのサブフォルダーは、.NET 用のドキュメントの構成と同じように整理されます。

コンテンツをサポートするコードについては、次のように区別しています。

- サンプル: 閲覧者はサンプルをダウンロードして実行することができます。 サンプルはすべて、完全なアプリケーションまたはライブラリである必要があります。 サンプルによってライブラリが作成される場合、それには単体テストか、または閲覧者がコードを実行するためのアプリケーションが含まれている必要があります。 多くの場合、サンプルでは複数のテクノロジ、機能、またはツールキットが使用されます。 各サンプルの readme.md には、各サンプル内で適用されている概念について詳細を確認できるように、記事への参照が含まれています。
- スニペット: より小さな概念またはタスクを示します。 これらはコンパイルされますが、完全なアプリケーションを意図したものではありません。 正しく実行される必要はありますが、代表的なシナリオに適したアプリケーションの例ではありません。 その代わり、単一の概念または機能を表現するために、可能な限り小さくなるように設計されます。 これらは、単一のコード画面に収める必要があります。

サンプルは [dotnet/samples](https://github.com/dotnet/samples) リポジトリに格納されています。 Microsoft では、samples フォルダーの構造が docs フォルダーの構造と一致するというモデルを目標に取り組んでいます。 Microsoft が従っている標準は次のとおりです。

- 最上位レベルのフォルダーは、*docs* リポジトリ内の最上位レベルのフォルダーと対応します。 たとえば、docs リポジトリに *machine-learning/tutorials* フォルダーがあるとすると、機械学習チュートリアルのサンプルは *samples/machine-learning/tutorials* フォルダーにあります。

さらに、*core* フォルダーおよび *standard* フォルダーの下に置くサンプルはすべて、.NET Core によってサポートされているすべてのプラットフォームでビルドされ実行される必要があります。 それは、Microsoft の CI ビルド システムによって強制されます。 最上位レベルの *framework* フォルダーには、Windows 上でのみビルドされ検証されるサンプルが含まれます。

サンプル プロジェクトは、特定のサンプルに対応する可能な限り広範囲のプラットフォーム上でビルドされ実行される必要があります。 それは実際には、可能な限り .NET Core ベースのコンソール アプリケーションをビルドすることを意味します。 Web フレームワークまたは UI フレームワークに固有のサンプルでは、必要に応じてそれらのツールが追加される必要があります。 たとえば、Web アプリケーション、モバイル アプリ、WPF または WinForms アプリなどがあります。

Microsoft は、すべてのコードに対応するように CI システムを整えることを目標に取り組んでいます。 サンプルに対して更新プログラムを作成する場合は、各更新プログラムを必ずビルド可能なプロジェクトに含めます。 理想的には、サンプル上に正確性のテストも追加します。

作成する完全なサンプルのそれぞれには、*readme.md* ファイルが含まれている必要があります。 このファイルには、サンプルに関する簡単な説明が含まれている必要があります (1 つまたは 2 つのパラグラフ)。 この *readme.md* では、このサンプルを探索することで何を学習できるのかを閲覧者に伝える必要があります。 *readme.md* ファイルには、[.NET ドキュメント サイト](https://docs.microsoft.com/dotnet/welcome)に掲載されているライブ ドキュメントへのリンクも含まれる必要があります。 リポジトリ内の特定のファイルがそのサイトのどこにマップされているかを確認するには、リポジトリ パス内の `/docs` を `https://docs.microsoft.com/dotnet` に置き換えます。

ご自分のトピックには、サンプルへのリンクも含められます。 GitHub 上のサンプルのフォルダーに直接リンクします。

### <a name="writing-a-new-sample"></a>新しいサンプルの作成

サンプルは、ダウンロード用の完全なプログラムとライブラリです。 これらは、スコープ内では小さくなることがありますが、ユーザーが自分で調査して実験できるようにするための概念を示しています。 サンプルのガイドラインに従うと、閲覧者がダウンロードして探索できるようになります。 各ガイドラインの例として、[Parallel LINQ (PLINQ)](https://github.com/dotnet/samples/tree/master/csharp/parallel/PLINQ) サンプルを確認してください。

1. 使用するサンプルは、**ビルド可能なプロジェクトの一部とする必要があります**。 可能な限り、プロジェクトは .NET Core によってサポートされているすべてのプラットフォーム上でビルドされる必要があります。 ただし、プラットフォーム固有の機能またはプラットフォーム固有のツールを実演するサンプルの場合は例外です。

2. 整合性を維持するために、使用するサンプルは [corefx コーディング スタイル](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md) に準拠する必要があります。

    - さらに、新しいオブジェクトのインスタンス化を必要としないものを実演する場合は、インスタンス メソッドではなく `static` メソッドの使用をお勧めします。

3. 使用するサンプルには、**適切な例外処理**を含める必要があります。 その例外処理によって、サンプルのコンテキスト内でスローされる可能性が高いすべての例外が処理される必要があります。 たとえば、[Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline) メソッドを呼び出してユーザー入力を取得するサンプルには、入力文字列が引数としてメソッドに渡されるときの適切な例外処理を使用する必要があります。 同様に、使用するサンプルでメソッド呼び出しの失敗が予想される場合は、結果としてスローされる例外を処理する必要があります。 [Exception](https://docs.microsoft.com/dotnet/api/system.exception) や [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception) などの基本クラスの例外ではなく、メソッドによってスローされる特定の例外を常に処理します。

4. 使用するサンプルによってスタンドアロン パッケージがビルドされる場合は、そのサンプルによって使用される任意のランタイムに加えて、Microsoft の CI ビルド システムによって使用されるランタイムも含める必要があります。
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Microsoft はこれらのプロジェクトをすぐにビルドできるように CI システムを調整していきます。

サンプルを作成するには:

1. [Issue](https://github.com/dotnet/docs/issues) を提出するか、または作業する既存の Issue にコメントを加えます。
2. 使用するサンプルで実演する概念を説明するトピックを記述します (例: `docs/standard/linq/where-clause.md`)。
3. 使用するサンプルを作成します (例: `WhereClause-Sample1.cs`).
4. そのサンプルを呼び出す Main エントリ ポイントを使用して Program.cs を作成します。 それがそこに既に存在する場合は、サンプルの呼び出しを追加します。

    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```

[.NET Core SDK](https://www.microsoft.com/net/download) を使用してインストールすることができる .NET Core CLI を使用して任意の .NET Core スニペットまたはサンプルを作成します。 使用するサンプルを作成し実行するには:

1. sample フォルダーに進み、エラーをチェックするために次をビルドします。

    ```console
    dotnet build
    ```
2. 使用するサンプルを実行します。

    ```console
    dotnet run
    ```

3. 使用するサンプルのルート ディレクトリに readme.md を追加します。

   このファイルでは、コードの概説を含めると共に、サンプルを参照している記事にユーザーの目を向ける必要があります。 *readme.md* の先頭には、[サンプルの参照](https://docs.microsoft.com/samples)に必要なメタデータが含まれている必要があります。 ヘッダー ブロックには、次のフィールドが含まれている必要があります。

   ```yml
   ---
   name: "really cool sample"
   description: "Learn everything about this really cool sample."
   page_type: sample
   languages:
     - csharp
     - fsharp
     - vbnet
   products:
     - dotnet-core
     - dotnet
     - dotnet-standard
     - aspnet
     - aspnet-core
     - ef-core
   ---
   ```

   - `languages` コレクションには、サンプルで使用できる言語のみを含める必要があります。
   - `products` コレクションには、サンプルに関連する製品のみを含める必要があります。

特別な記載のない限り、すべてのサンプルは .NET Core によってサポートされている任意のプラットフォーム上のコマンド ラインからビルドされます。 Visual Studio に固有のサンプルであり、Visual Studio 2017 以降を必要とするサンプルがいくつかあります。 さらに、サンプルの中にはプラットフォーム固有の機能を示し、特定のプラットフォームを必要とするものもあります。 他に、.NET Framework を必要とし、Windows プラットフォーム上で実行され、Framework 対象バージョン用の Developer Pack を必要とするサンプルとスニペットもあります。

## <a name="the-c-interactive-experience"></a>C# インタラクティブ エクスペリエンス

記事に含めるすべてのサンプルで、ソース言語を示すための[言語タグ](../code-in-docs.md)が使用されます。 C# による短いコード サンプルでは、`csharp-interactive` 言語タグを使用して、ブラウザー内で実行される C# サンプルを指定することができます。 (インライン コード サンプルでは `csharp-interactive` タグが使用され、ソースから取り込まれるスニペットの場合は、`code-csharp-interactive` タグが使用されます。)これらのコード サンプルでは、記事内のコード ウィンドウと出力ウィンドウが表示されます。 ユーザーがサンプルを実行すると、インタラクティブ コードの実行から得られる任意の出力が出力ウィンドウに表示されます。

C# インタラクティブ エクスペリエンスによって、サンプルを操作する方法が変更されます。 訪問者は、サンプルを実行して結果を表示することができます。 サンプルまたは対応するテキストに出力に関する情報を含める必要があるかどうかを判断するのに役立つ要因が複数あります。

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>サンプルを実行することなしに期待される出力を表示するタイミング

- 初心者を対象にした記事では、閲覧者が自分の作業の出力を期待される答えと比較できるように出力が示される必要があります。
- トピックに出力が欠かせないサンプルでは、その出力が示される必要があります。 たとえば、書式付きテキストに関する記事では、サンプルを実行することなくテキスト書式が示される必要があります。
- サンプルも期待される出力も短い場合は、出力を示すことを検討してください。 それによって若干の時間が節約されます。
- 現在のカルチャまたはインバリアント カルチャが出力に及ぼす影響を説明する記事では、期待される出力を説明する必要があります。 インタラクティブ REPL (Read Evaluate Print Loop) は Linux ベースのホストで実行されます。 既定のカルチャとインバリアント カルチャにより、各種オペレーティング システムおよびマシン上でそれぞれ異なる出力が作成されます。 記事では、Windows、Linux、Mac システムでの出力を説明する必要があります。

### <a name="when-to-exclude-expected-output-from-the-sample"></a>期待される出力をサンプルから除外するタイミング

- サンプルによって大きな出力が作成される記事では、コメント内にそのサンプルを含めないでください。 サンプルが実行されると、コードがわかりにくくなるからです。
- サンプルによってトピックが実演されるが、トピックを理解する上で出力は不可欠であるとは言えない記事。 たとえば、クエリ構文を説明し出力コレクション内にすべてのアイテムを示すために LINQ クエリを実行するコード。

> [!NOTE]
> 一部のトピックがここで指定したすべてのガイドラインに現在のところ従っていないことに気づかれているのではないでしょうか。 Microsoft はサイト全体での整合性の達成を目標に取り組んでいます。 その特定の目標を達成するために Microsoft が現在追跡している [開示状態の Issues](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22) の一覧を確認してください。

### <a name="contributing-to-international-content"></a>海外のコンテンツへの貢献

機械翻訳 (MT) コンテンツの投稿は、現在受け入れられていません。 MT コンテンツの品質を向上させるために、ニューラル MT エンジンに移行しました。 ニューラル MT エンジンをトレーニングするために使用される、人間が翻訳した (HT) コンテンツの投稿を受け入れ、促進することをお勧めします。 今後、HT コンテンツに貢献すると、HT と MT の両方の品質が向上します。 MT トピックには、トピックの一部が MT であることを示す免責事項が含まれており、編集が無効になっているため **[編集]** ボタンが表示されません。

## <a name="contributor-license-agreement"></a>共同作成者使用許諾契約書

ご自分の PR がマージされる前に、[.NET Foundation 共同作成使用許諾契約書 (CLA)](https://cla.dotnetfoundation.org) に署名する必要があります。 これは、.NET Foundation 内のプロジェクトに対して一度だけ必要です。 詳細については、Wikipedia 上の [共同作成使用許諾契約書 (CLA)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) に関するページを参照してください。

契約: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

事前に契約書に署名しておく必要はありません。 通常どおり、ご自分の PR を複製、フォーク、送信することができます。 ご自分の PR が作成されたら、それを CLA ボットによって分類することができます。 変更が小さい場合 (たとえば、入力ミスの修正)、PR には `cla-not-required` というラベルが適用されます。 それ以外の場合は、`cla-required` として分類されます。 CLA に署名すると、現在および将来のすべての Pull requests に `cla-signed` のラベルが付けられます。