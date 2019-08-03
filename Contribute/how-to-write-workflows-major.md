---
title: 大規模な変更や長期にわたる変更の GitHub 共同作成ワークフロー
description: この記事では、"大規模な" 共同作成者向けのワークフローを利用して docs.microsoft.com の記事を作成する方法について説明します。
ms.date: 08/30/2017
ms.openlocfilehash: 93e659df4f72c6a272d15fd7487eb3a997bdf3c8
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609407"
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>大規模な変更や長期にわたる変更の GitHub 共同作成ワークフロー

> [!IMPORTANT]
> docs.microsoft.com に公開されるすべてのリポジトリには、「[Microsoft Open Source Code of Conduct (Microsoft オープンソース倫理規定)](https://opensource.microsoft.com/codeofconduct/)」または「[.NET Foundation Code of Conduct (.NET Foundation 倫理規定)](https://dotnetfoundation.org/code-of-conduct)」が適用されています。 詳細については、「[Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/)」 (倫理規定に関する FAQ) を参照してください。 または、ご質問やコメントがある場合は、[opencode@microsoft.com](mailto:opencode@microsoft.com) または [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) までご連絡ください。<br>
>
> パブリック リポジトリ内にあるドキュメントおよびコード例の軽微な修正や補足は、「[docs.microsoft.com - 使用条件](https://docs.microsoft.com/legal/termsofuse)」の対象になります。 Microsoft の従業員ではない共同作成者が新規または大幅な変更を行うと、オンライン貢献者使用許諾契約書 (CLA) の提出をお願いするコメントがプルリクエスト内に生成されます。 プルリクエストをマージするには、オンライン フォームへの入力が必要になります。

## <a name="overview"></a>概要

このワークフローは、大規模な変更を行う必要がある共同作成者や、リポジトリへの変更を頻繁に行う共同作成者に適しています。 概して、頻繁に作業をする共同作成者とは、プルリクエストのサインオフとマージに至るまでに、ビルド/検証/ステージングのサイクルを何度も繰り返す継続的な (長期間にわたる) 変更や、何日もかかる変更を抱えている共同作成者のことです。

このタイプの共同作成の例:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>用語集

始める前に、このワークフローで使用される Git/GitHub の用語とモニカーをいくつか説明します。 それらをすぐに理解できなくても気にすることはありません。 それらの知識を得ておくことにより、定義を確認する必要が生じたときには、このセクションを再び参照できます。

| 名前 | 説明 |
|-----------|-------------|
|フォーク|通常では、メイン GitHub リポジトリのコピーを指すときに、名詞として使用されます。 実際には、フォークは別のリポジトリです。 ただし、GitHub でメイン/親リポジトリへの接続が維持される点で、これは特殊です。 "最初にリポジトリをフォークする必要があります" のように、動詞として使用されることも時々あります。|
|リモート|リモート リポジトリへの名前付きの接続です。たとえば、"オリジン" リモートや "アップストリーム" リモートです。 Git では、これは別のコンピューターでホストされているリポジトリへの参照に使用されるため、"リモート" と呼ばれます。 このワークフローでは、リモートはいつでも GitHub リポジトリです。|
|オリジン|独自のローカル リポジトリとその複製元リポジトリとの間の接続に割り当てられた名前です。 このワークフローでのオリジンは、独自のフォークへの接続を表します。 "忘れずに変更をオリジンにプッシュしてください" のように、オリジン リポジトリ自体のモニカーとして使用されることも時々あります。|
|アップストリーム|オリジン リポジトリと同様に、アップストリームとは別のリポジトリへの名前付きの接続のことです。 このワークフローでのアップストリームは、独自のローカル リポジトリと、独自のフォークを作成したときの基となったメイン リポジトリとの間の接続を表します。 "忘れずにアップストリームから変更をプルしてください" のように、アップストリーム リポジトリ自体のモニカーとして使用されることも時々あります。|

## <a name="workflow"></a>ワークフロー

>[!IMPORTANT]
> [セットアップ](get-started-setup-github.md)に関するセクションの手順を完了していない場合は、それらを完了する必要があります。 このセクションでは、GitHub アカウントのセットアップ、Git Bash と Markdown エディターのインストール、フォークの作成、およびローカル リポジトリのセットアップに関する手順が説明されています。 リポジトリやブランチなど、Git と GitHub の概念をよく知らない場合は、最初に [Git と GitHub の基本](git-github-fundamentals.md)に関するページを確認してください。

このワークフローでは、繰り返されるサイクルの中で変更内容が推移します。 変更内容は、ご利用のデバイスのローカル リポジトリから出て、独自の GitHub フォークに戻り、メイン GitHub リポジトリに入り、ほかの共同作成者による変更内容を取り込んでローカルに再び戻ります。

### <a name="use-github-flow"></a>GitHub フローを使用する

[Git と GitHub の基本](git-github-fundamentals.md#git)に関するページの説明から、Git リポジトリにはマスター ブランチのほかに、マスターに取り込まれていない進行中の作業ブランチがあることを思い出してください。 論理的に関連性のある複数の変更内容を導入するときのベスト プラクティスは、ワークフローに従って独自の変更内容を管理するための "*作業ブランチ*" を作成することです。 これはマスター ブランチに再統合できるようになるまで変更内容を反復/改善するためのワーク スペースであることから、ここでは作業ブランチと呼ばれます。

関連性のある変更内容を特定のブランチに分離することにより、公開サイクル内の具体的なリリース時期に合わせてそれらの変更内容を個別に管理して導入できます。 実際に、実施する作業の種類によっては、独自のリポジトリ内に複数の作業ブランチが存在するようになることがよくあります。 それぞれに異なるプロジェクトの作業が、複数のブランチで同時に進行するのは珍しいことではありません。

>[!TIP]
>'マスター' ブランチで独自の変更を行うのは、得策では*ありません*。 リリース日が決まっている機能リリースに複数の変更内容を導入するために、マスター ブランチを使用することを考えてみてください。 変更作業を終えて、リリースを待っているとします。 その間に、緊急の修正要求があったため、マスター ブランチ内のファイルに変更を行ってから、その変更内容を公開します。 この例では、特定の日にリリースするために保留していた変更内容*と*修正プログラムの両方を意図せず公開してしまいます。

それでは、独自の変更案を取り込むために、独自のローカル リポジトリに新しい作業ブランチを作成しましょう。 各 git クライアントが異なるので、使用するクライアントのヘルプをご覧ください。 [GitHub フロー](https://guides.github.com/introduction/flow/)について、GitHub ガイドでプロセスの概要を参照できます。

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>次のステップ

これで終了です。 docs.microsoft.com のコンテンツを共同作成しました。

- Markdown や Markdown 拡張構文などのトピックについての知識を深めるには、「Writing essentials」 (書き方の要点) セクションに進んでください。
