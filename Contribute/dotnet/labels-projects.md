---
title: ラベルとプロジェクトのロードマップ
description: この記事では、dotnet/docs リポジトリでラベルおよびプロジェクトを使用する方法について説明します。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
ms.date: 03/24/2020
ms.openlocfilehash: 0dcac28db04378730b186c0f23064c1433d9f80e
ms.sourcegitcommit: bf2f4c7d9050b480d4db306df19d4c9f8714eff0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80760378"
---
# <a name="labels-and-projects-roadmap"></a>ラベルとプロジェクトのロードマップ

NET docs チームでは、[GitHub ラベル](https://github.com/dotnet/docs/labels) を広く利用して、作業を整理しています。 ラベルの組み合わせに基づいてフィルター処理することで、[.NET docs Web サイト](https://docs.microsoft.com/dotnet) 上の関心のあるセクションにすばやくフォーカスできます。

また、スプリントやその他のゴール指向のエピックを整理するために、[GitHub プロジェクト](https://github.com/dotnet/docs/projects)も使用しています。

このロードマップでは、これらの整理ツールを使用する方法について説明し、関心のある領域を見つけ出すために使用する便利なフィルターへのリンクを示します。

## <a name="labels"></a>ラベル

[dotnet/docs](https://github.com/dotnet/docs) に初めて投稿する場合は、[up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) のイシューから始めます。 これらは、範囲をさらに絞ったイシューであり、 最初の投稿に非常に適しています。 up-for-grabs ビューで、分野や優先度に基づいてイシューをさらにフィルター処理することができます。 最初に短い投稿を試す場合のために、Microsoft では、初心者に適したイシューを [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) で特定しています。

Microsoft では、ラベルを使用して、さまざまな方法でイシューを分類しています。

- [.NET ガイド](#find-a-single-net-guide)と[ガイドのセクション](#search-one-section-of-a-guide)。
- [ターゲット リリース](#releases)
- [優先度](#priority)

投稿するイシューを見つけるために、各セットのラベル (ガイド、リリース、優先度) を組み合わせて範囲を絞ることができます。

### <a name="find-a-single-net-guide"></a>単一の .NET ガイドを検索する

Microsoft では、アーキテクチャに関する各電子書籍および各 .NET ガイドにラベルを使用しています。

![:book: 明るい緑色の背景に guide の文字](./media/labels-projects/guide.png "アーキテクチャ ガイドのプレフィックス")

アーキテクチャに関する電子書籍には、`:book: guide`プレフィックスが付けられ、背景は明るい緑色です。 これらは、推奨アーキテクチャについて説明する長文の領域です。 各 .NET アーキテクチャ ガイドについてフィルター処理された現在のイシューを次に示します。

- [ASP.NET Core Web アプリ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [クラウド ネイティブ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Docker のライフサイクル](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [Windows コンテナーによる最新化](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [.NET マイクロサービス](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [サーバーレス アプリ](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

このラベル スタイルは、[フレームワーク デザイン ガイドライン](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)にも適用されます。 この領域のラベルも同じデザインですが、コミュニティ PR は推奨されません。 これは、許可を得て再印刷される資料で、編集することはできません。

![:books: 濃い青色の背景に Area の文字](./media/labels-projects/area.png ".NET ガイドの領域ラベルのプレフィックス")

各 .NET ガイドには、`:books: Area` プレフィックスが付けられ、背景は濃い青色です。 各 .NET ガイドについてフィルター処理された現在のイシューを次に示します。

- [API リファレンス](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [Azure .NET SDK](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [C# ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [デスクトップ ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [F# ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [ML.NET ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [.NET アーキテクチャ ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 削除される可能性がある
- [.NET Core ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [.NET for Apache Spark ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [.NET フレームワーク ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [.NET ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Roslyn API リファレンス](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 削除される可能性があります。
- [Visual Basic ガイド](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>ガイドの 1 つのセクションを検索する

![:card_file_box: ミディアム ブルーの背景に Area の文字](./media/labels-projects/technology.png ".NET ガイドのサブ領域ラベルのプレフィックス")

.NET ガイドは大きいため、これらのラベルは、ガイドのセクション別に範囲をさらに限定します。 .NET ガイドの各サブ領域には、`:card_file_box: Technology` プレフィックスが付けられ、背景はミディアム ブルーです。 これらのラベルの多くは、複数のガイドに適用されますが、その他のラベルは、1 つのガイドにのみ含まれます。 領域でフィルター処理した後、以下のラベルのいずれかを追加して、イシューの範囲をさらに限定します。

- AppCompat
- 非同期タスク
- C# の高度な概念
- C# コンパイラ
- C# の基礎
- C# 入門
- C# 言語リファレンス
- C# の Null 安全
- C# の新機能
- CLI
- データ アクセス
- Docker
- インストーラ
- LINQ
- NCL
- .NET Standard
- Roslyn API
- セキュリティ
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>リリース

![:checkered_flag: 濃い黄色に Release の文字](./media/labels-projects/release.png "リリース ラベルのプレフィックス")

特定のリリースのタグが付けられたイシューには、`:checkered_flag: Release:` プレフィックスが付けられ、背景は濃い黄色です。

- .NET Core 2.2
- .NET Core 3.0
- .NET Framework 4.8
- .NET 5

### <a name="priority"></a>優先度

優先度ラベルはすべて `P`とその後に 1 桁の数字が続きます。 小さい数字の方が、優先度は高くなります。

- P0
- P1
- P2
- P3

### <a name="what-about-the-other-labels"></a>その他のラベルについて

コンテンツ チームがイシューのさまざまな分類を管理するために使用するラベルは、他にも多数あります。 コンテンツ チームに属していない場合は、これらの他のラベルを無視してかまいません。

## <a name="projects"></a>プロジェクト

プロジェクトは、次の 2 つの方法で使用します。

- 月 YYYY プロジェクトの種類: これらは、各月の作業計画用のスクラム ボードです。
- 長期間のエピック: これらは、作業が数か月にわたって行われる場合に、ゴールに向けたタスクの整理に使用されます。
