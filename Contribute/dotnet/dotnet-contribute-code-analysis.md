---
title: .NET コード分析規則に関するドキュメントを .NET ドキュメント リポジトリに投稿する
description: この記事では、.NET ドキュメント レポジトリで .NET コード分析規則に関する記事やコード サンプルに協力する過程について説明します。
author: mavasani
ms.author: mavasani
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 10/09/2020
ms.openlocfilehash: 27ae1a31c55c41aa1c97bf1f88dbf28bec35a80a
ms.sourcegitcommit: f1535713b66ff9b840f1138583746bc2bf182b4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957056"
---
# <a name="contribute-docs-for-net-code-analysis-rules-to-the-net-docs-repository"></a>.NET コード分析規則に関するドキュメントを .NET ドキュメント リポジトリに投稿する

.NET のコンパイラ プラットフォーム (Roslyn) アナライザーでは、お使いの C# または Visual Basic コードについて、コード品質やコード スタイルに関する問題を検査できます。 .NET 5.0 以降、これらのアナライザーは [.NET SDK に含まれる](/dotnet/fundamentals/code-analysis/overview)ようになりました。

- [コード品質分析 ("CAxxxx" 規則)](/dotnet/fundamentals/code-analysis/overview#code-quality-analysis):
  - [こちらの](https://github.com/dotnet/roslyn-analyzers/tree/master/src/NetAnalyzers) `dotnet/roslyn-analyzers` リポジトリで実装されています。
  - [こちらの](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/quality-rules) `dotnet/docs` リポジトリでドキュメント化されています。 「['CAxxxx' 規則に関するドキュメントを投稿する](#contribute-docs-for-caxxxx-rules)」をご覧ください。
- [コード スタイル分析 ("IDExxxx" 規則)](/dotnet/fundamentals/code-analysis/overview#code-style-analysis):
  - [こちらの](https://github.com/dotnet/roslyn/tree/master/src/Analyzers) `dotnet/roslyn` リポジトリで実装されています。
  - [こちらの](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/style-rules) `dotnet/docs` リポジトリでドキュメント化されています。 「['IDExxxx' 規則に関するドキュメントを投稿する](#contribute-docs-for-idexxxx-rules)」をご覧ください。

## <a name="contribute-docs-for-caxxxx-rules"></a>'CAxxxx' 規則に関するドキュメントを投稿する

コード品質分析規則に関するドキュメントを [dotnet/docs](https://github.com/dotnet/docs) リポジトリに投稿するには、次の手順に従ってください。

1. `Rule ID` と `Category` の決定:ドキュメント化する規則の 'CAxxxx' 規則 ID とカテゴリがわかっていることを確認します。 これは、CA アナライザーが [dotnet/roslyn-analyzers](https://github.com/dotnet/roslyn-analyzers) リポジトリにマージされているか、規則に割り当てられている承認済みの ID とカテゴリを持つオープン PR があることを意味します。
2. 規則のドキュメントの追加:
   1. [ルート](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/quality-rules) フォルダー下にある既存の CA 規則ファイル (たとえば `ca1000.md`) を複製し、名前を変更します。
   2. ファイルの内容を適切に更新します。
3. 次の表に、規則のエントリを追加します。
   - 規則のカテゴリ一覧の[目次](https://github.com/dotnet/docs/blob/master/docs/fundamentals/toc.yml)ファイル。 たとえば、`Performance` カテゴリの CA 規則の場合は、ファイルで用語 `- name: Performance rules` を検索し、一覧にエントリを追加します。 存在しない場合は、`- name: Code quality rules` で新しいカテゴリの一覧を作成します。
   - [最上位レベルの規則インデックス](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/quality-rules/index.md) ファイル。
   - `category` ベースの規則インデックス ファイル:
     1. [ルート](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/quality-rules) フォルダーで、カテゴリ ベースのインデックス ファイルを特定します。 たとえば、`Performance` カテゴリの CA 規則の場合、このファイルには `performance-warnings.md` という名前が付けられます。 存在しない場合は、既存のものを複製して新しいカテゴリ ベースのインデックス ファイルを作成します。
     2. このファイルに規則 ID のエントリを追加します。

> [!TIP]
> `dotnet/docs` リポジトリで、既知の既存の CA 規則 ID についてリポジトリ検索を実行し、更新が必要な可能性のある場所を特定します。 例については、「 <https://github.com/dotnet/docs/search?q=CA2000>」を参照してください。

## <a name="contribute-docs-for-idexxxx-rules"></a>'IDExxxx' 規則に関するドキュメントを投稿する

コード スタイル分析規則に関するドキュメントを [dotnet/docs](https://github.com/dotnet/docs) リポジトリに投稿するには、次の手順に従ってください。

1. `Rule ID` とコード スタイルのオプションを決定します (存在する場合)。ドキュメント化する規則の 'IDExxxx' 規則 ID とコード スタイルのオプションがわかっていることを確認します。 これは、IDE アナライザーが [dotnet/roslyn](https://github.com/dotnet/roslyn) リポジトリにマージされているか、規則に割り当てられている承認済みの ID とコード スタイルのオプションを持つオープン PR があることを意味します。
2. 規則 `subcategory` の決定:IDE 規則にはカテゴリ `Style` があります。 規則のサブカテゴリを確認するには、「[コード スタイル規則](/dotnet/fundamentals/code-analysis/style-rules/index)」の概要セクションを参照してください。 ほとんどの IDE コード スタイル規則は `Language` サブカテゴリの下にあります。
3. 規則 `preference group` の決定:[こちら](/dotnet/fundamentals/code-analysis/style-rules/language-rules#net-style-rules)に記載されている基本設定ヘッダーを参照して、規則の `preference group` を確認します。
   - 規則に既知の、関連付けられたコード スタイルのオプションがある場合、基本設定グループは、コード スタイルのオプションの宣言で指定されている `OptionGroup` と一致します。
   - それ以外の場合は、規則が既存の基本設定グループに属しているか、または新しい基本設定グループが必要かどうかを確認します。
4. 規則のドキュメントの追加:
   1. [ルート](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/style-rules) フォルダー下にある既存の IDE 規則ファイル (たとえば `ide0011.md`) を複製し、名前を変更します。
   2. ファイルの内容を適切に更新します。
5. 次の表に、IDE 規則や、コード スタイルのオプションに関するエントリを追加します。
   - 規則のサブカテゴリと基本設定の一覧の下にある[目次](https://github.com/dotnet/docs/blob/master/docs/fundamentals/toc.yml)ファイル。 たとえば、`Language` サブカテゴリと `Modifier preferences` グループを持つ IDE コード スタイル規則の場合は、ファイルで用語 `- name: Language rules` と子ノード `- name: Modifier preferences` を検索し、一覧にエントリを追加します。 サブカテゴリの一覧、またはサブカテゴリの下にある基本設定の一覧のいずれかが存在しない場合は、`- name: Code style rules` の下に新しく作成します。
   - [コード スタイルのオプション ベースのインデックス](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/style-rules/language-rules.md) ファイル。
   - [規則 ID ベースのインデックス](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/style-rules/index.md) ファイル。
   - `preferences group` ベースの規則インデックス ファイル:
     1. [ルート](https://github.com/dotnet/docs/blob/master/docs/fundamentals/code-analysis/style-rules) フォルダーで、基本設定グループ ベースのインデックス ファイルを特定します。 たとえば、`Modifier preferences` の IDE 規則の場合、このファイルには `modifier-preferences.md` という名前が付けられます。 存在しない場合は、既存のものを複製して新しい基本設定グループ ベースのインデックス ファイルを作成します。
     2. このファイルに規則 ID のエントリを追加します。

> [!TIP]
> `dotnet/docs` リポジトリで、既知の既存の IDE 規則やコード スタイルのオプションについてリポジトリ検索を実行し、更新が必要な可能性のある場所を特定します。 たとえば、 <https://github.com/dotnet/docs/search?q=IDE0011> や <https://github.com/dotnet/docs/search?q=csharp_prefer_braces>を参照してください。

## <a name="see-also"></a>関連項目

- [.NET ドキュメント リポジトリに協力する](dotnet-contribute.md)
