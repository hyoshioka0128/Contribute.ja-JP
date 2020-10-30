---
title: ラベル、プロジェクト、マイルストーンのロードマップ
description: この記事では、dotnet/docs リポジトリでラベル、プロジェクト、およびマイルストーンを使用する方法について説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 08/06/2020
ms.openlocfilehash: 059ed8297956589a281cf11e4f7244e972565160
ms.sourcegitcommit: 11228bd1d3dc1496820355096453f1eb2d28b33e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92523472"
---
# <a name="labels-projects-and-milestones-roadmap"></a>ラベル、プロジェクト、マイルストーンのロードマップ

NET docs チームでは、[GitHub ラベル](https://github.com/dotnet/docs/labels) を広く利用して、作業を整理しています。 ラベルの組み合わせに基づいてフィルター処理することで、[.NET docs Web サイト](https://docs.microsoft.com/dotnet) 上の関心のあるセクションにすばやくフォーカスできます。 たとえば、開示状態の優先度 1 `P1` の issue すべてに対してフィルター処理を行うには、次のクエリを使います: [is:issue is:open label:":books:Area - .NET Architecture Guide"](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3A%22%3Abooks%3A+Area+-+.NET+Architecture+Guide%22)。

私たちは、スプリントやその他のゴール指向のエピックを整理するために、[GitHub プロジェクト](https://github.com/dotnet/docs/projects)を使用しています。 また、作業を追跡するために [GitHub マイルストーン](https://github.com/dotnet/docs/milestones)も使用しています。 プロジェクトは計画用 (issue)、マイルストーンは作業用 (pull request) と考えることをお勧めします。

このロードマップでは、これらの組織ツールの使用方法について説明するほか、目的の領域を見つけるために使用できる便利なフィルターへのリンクも用意されています。

## <a name="labels"></a>ラベル

これが [dotnet/docs](https://github.com/dotnet/docs) に投稿する初めての経験である場合は、[up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) イシューから開始してください。 これらは、より範囲が絞られたイシューです。 これは、最初の投稿を作成するのに最適な方法です。 up-for-grabs ビューから、領域や優先度に基づいてイシューをさらにフィルター処理できます。 最初の投稿を小さくする必要がある場合は、[good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) を持つ初心者向けの適切なイシューが特定されています。

ラベルを使用して、さまざまな方法でイシューを分類します。

- [.NET ガイド](#find-a-single-net-guide) と [ガイドのセクション](#search-one-section-of-a-guide)。
- [ターゲット リリース](#releases)
- [優先順位](#priority)

各セット (ガイド、リリース、優先順位) からのラベルを組み合わせて、範囲を絞って作業対象のイシューを見つけることができます。

### <a name="find-a-single-net-guide"></a>単一の .NET ガイドを検索する

アーキテクチャ電子書籍ごとに、および .NET ガイドごとにラベルを使用します。

![:book: guide、明るい緑色の背景](./media/labels-projects/guide.png "アーキテクチャ ガイド ラベルのプレフィックス")

アーキテクチャの電子書籍には、`:book: guide` プレフィックスが付いていて、背景は明るい緑色になっています。 これらは、推奨アーキテクチャをカバーする長い形式の領域です。 .NET アーキテクチャ ガイドごとにフィルター処理された現在のイシューを以下に示します。

- [ASP.NET Core Web アプリ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [クラウド ネイティブ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Docker ライフサイクル](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [w/ Windows コンテナーの最新化](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [.NET マイクロサービス](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [サーバーレス アプリ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

このラベル スタイルは、[フレームワーク デザインのガイドライン](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)にも適用されます。 この領域には同じラベル デザインがありますが、コミュニティ PR はお勧めしません。 これは許可を得て転載された資料です。編集しないでください。

![:books: 濃い青色の背景に Area の文字](./media/labels-projects/area.png ".NET ガイド領域ラベルのプレフィックス")

各 .NET ガイドには `:books: Area` プレフィックスが付いていて、背景は濃い青色になっています。 .NET ガイドごとにフィルター処理された現在のイシューを以下に示します。

- [API リファレンス](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [Azure .NET SDK](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [C# のガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [デスクトップ ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [F# のガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [ML.NET ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [.NET アーキテクチャ ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 削除可能です
- [.NET Core のガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [.NET for Apache Spark ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [.NET Framework ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [.NET のガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Roslyn API リファレンス](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 削除可能です。
- [Visual Basic のガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>ガイドの 1 つのセクションを検索する

![:card_file_box: ミディアム ブルーの背景に Area の文字](./media/labels-projects/technology.png ".NET ガイド サブ区分ラベルのプレフィックス")

.NET ガイドは大きいので、これらのラベルでは、ガイドのセクションによってスコープがさらに制限されます。 各 .NET ガイドのサブ領域には `:card_file_box: Technology` プレフィックスが付いていて、背景は中程度の濃さの青色になっています。 これらのラベルの多くは複数のガイドに適用されますが、他は 1 つのガイドにのみ含まれます。 領域をフィルター処理したら、以下のラベルのいずれかを追加して、イシューの範囲をさらに制限します。

- AppCompat
- 非同期タスク
- C# の詳細な概念
- C# コンパイラ
- C# の基礎
- C# はじめに
- C# 言語リファレンス
- C# Null 安全性
- C# 新機能
- CLI
- データ アクセス
- Docker
- インストーラー
- LINQ
- NCL
- .NET Standard
- Roslyn API
- Security
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>リリース

![:checkered_flag: 濃い黄色に Release の文字](./media/labels-projects/release.png "リリース ラベルのプレフィックス")

特定のリリースにタグが付けられたイシューには、`:checkered_flag: Release:` プレフィックスが付いていて、背景は濃い黄色になっています。

- .NET Core 2.2
- .NET Core 3.0
- .NET Framework 4.8
- .NET 5

### <a name="priority"></a>優先度

優先順位ラベルはすべて、`P` の後に 1 桁の数字が続きます。 数値が小さいほど優先度が高くなります。

- P0 - 重大な優先度

  セキュリティ イシュー、またはコンプライアンスのために法的に必要です。 他のすべてに優先して修正されます。
  
- P1 - 高優先度

  一般的なシナリオにおいて不可欠です。 または、ページ ビューが多い記事で非常に目立つエラーです。 これらは P2 や P3 の作業の前に実行されます。
  
- P2 - 中程度の優先度

  一般的なシナリオにおいて役立ちますが、妨げになるほどではありません。  これらは、すばやく簡単に作業できる場合、または同じ記事内の P1 のイシューに対処するのと同時に実行されます。
  
- P3 - 低優先度

  特殊なケースで役に立つ、一般的なシナリオにおいてささいな修正である、ページ ビューが少ない記事、または非推奨のテクノロジ。 私たちが作業することはありませんが、コミュニティのメンバーは自由に貢献できます。 P3 のイシューは、2 か月後に対処されていない場合は閉じられる可能性があります。

### <a name="what-about-the-other-labels"></a>その他のラベルについて

イシューのさまざまな分類を管理するためにコンテンツ チームが使用するラベルが他にも多数あります。 コンテンツ チームに所属していない場合、そのような他のラベルは無視してかまいません。

## <a name="projects"></a>プロジェクト

プロジェクトは計画を目的としており、かんばんボードを通じて優先的な作業が自動化されます。 プロジェクトには、GitHub の issue のみを含める必要があります。pull request は " _含めません_ "。 プロジェクトはマイルストーンとは異なります。マイルストーンに含めるのは pull request のみです。

プロジェクトは、次の 2 つの方法で使用します。

- `Month YYYY` プロジェクトの種類:これらは、各月の作業計画用のかんばんボードです。
  - 例: [July 2020](https://github.com/dotnet/docs/projects/103)、[August 2020](https://github.com/dotnet/docs/projects/117) など。
- 長期間のエピック: これらは、作業が数か月にわたって行われる場合に、ゴールに向けたタスクの整理に使用されます。
  - 例: [.NET 5 Wave - Reorganization](https://github.com/dotnet/docs/projects/105)、[.NET Languages (.NET 5 wave)](https://github.com/dotnet/docs/projects/106) など。

## <a name="milestones"></a>マイルストーン

通常、マイルストーンはプロジェクトと同じ名前付け規則 `Month YYYY` に従いますが、プロジェクトとは異なります。 マイルストーンは、完了した作業を追跡するために使用されます。 マイルストーンには issue (潜在的な作業) を " _含めません_ "。pull request だけを含める必要があります。 現在のマイルストーンは、自動的に新しい pull request に適用されます。
