---
title: validation-timeout
description: Docs のビルドに関するイシュー validation-timeout の説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 6/5/2019
ms.prod: non-product-specific
ms.openlocfilehash: 9f8074d3746ea375e29704853c82f48d95273cdc
ms.sourcegitcommit: 55624c641bea5367bcfa08655c085bc950e8beae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73166771"
---
# <a name="validation-timeout"></a>validation-timeout

## <a name="warning"></a>警告

`The call to the validation service timed out and validation was not completed. This happens when there's an issue with the service and continuing to retry the call could cause build delays. You might have content issues that were not reported. To retry validation, close and re-open your PR, or force a full build of your branch via https://ops.microsoft.com. Note that forcing a full build requires admin permissions to the repo. If you don’t know who your repo admin is, or if you continue to see this message after a forced build, file an issue via https://SiteHelp.`

サーバーが正常な状態ではない場合など、検証サービスの一時的なイシューによって、Docs のビルドによりそのサービスを正常に呼び出せない場合があります。 ビルドの遅延やビルド パイプラインの渋滞を回避するために、数回の試行の後、呼び出しはタイムアウトになり、検証はキャンセルされます。

## <a name="resolution"></a>解決方法

PR を閉じて、もう一度開いてみてください。または [Docs Portal](https://ops.microsoft.com/#/) から完全なビルドを強制的に実行してみてください。 多くの場合、最初の再試行後に、サービスのイシューは自動的にクリアされます。

Docs Portal からビルドを強制的に実行するには、リポジトリ管理者である必要があります。 お客様が Microsoft の従業員で、誰がリポジトリ管理者かわからない場合、または強制ビルド後もメッセージが表示される場合は、[https://SiteHelp](https://SiteHelp) 経由でイシューをご提出ください。お客様が外部の共同作成者である場合は、ご自分の PR 内で記事の作成者を @ で言及し、サポートをご依頼ください。

リポジトリ管理者は、次のようにして完全なビルドを強制的に実行することができます。

1. [Docs Portal](https://ops.microsoft.com/#/) ポータルに移動し、サインインします。
1. 左上隅でリポジトリを検索し、それを選択します。

   :::image type="content" source="media/find-repo.png" alt-text="Docs Portal の検索ボックスを使用してリポジトリを検索する":::
1. **[ビルド履歴]** タブで、 **[+ Manual Publish]\(+ 手動での発行\)** をクリックします。
1. 警告が発生しているブランチ (Master など) を選択します。
1. ターゲットは、既定の **[Docs site]\(Docs サイト\)** をそのまま使用します。
1. **[強制発行]** チェックボックスをオンにします。
1. **[発行]** をクリックします。

   :::image type="content" source="media/force-build.png" alt-text="完全なビルドを強制的に実行するステップ":::

これにより、ブランチで完全なビルドが強制的に実行されます。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
