---
title: validation-timeout
description: Docs のビルドに関するイシュー validation-timeout の説明と解決方法
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 6/5/2019
ms.prod: non-product-specific
ms.openlocfilehash: bb58c472371c429002cf5b35b7d6157ffb28b5cd
ms.sourcegitcommit: 495d49f10df51a8897687940aa653e906c48c2a0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817419"
---
# <a name="validation-timeout"></a>validation-timeout

## <a name="warning"></a>警告

`The call to the validation service timed out and validation was not completed. This happens when there's an issue with the service and continuing to retry the call could cause build delays. You might have content issues that were not reported. To retry validation, close and re-open your PR, or rebuild your branch via Docs Portal (requires admin permissions). If you need admin help or if you continue to see this message, file an issue via https://SiteHelp.`

サーバーが正常な状態ではない場合など、検証サービスの一時的なイシューによって、Docs のビルドによりそのサービスを正常に呼び出せない場合があります。 ビルドの遅延やビルド パイプラインの渋滞を回避するために、数回の試行の後、呼び出しはタイムアウトになり、検証はキャンセルされます。

## <a name="resolution"></a>解決方法

PR を閉じてからもう一度開いてみます。または Docs ポータルを使用して手動ビルドを再実行します (リポジトリ管理者のみ)。 多くの場合、最初の再試行後に、サービスのイシューは自動的にクリアされます。 管理者のヘルプが必要、または引き続きメッセージが表示される場合、お客様が Microsoft の従業員である場合は、[https://SiteHelp](https://SiteHelp) 経由でイシューをご提出ください。お客様が外部の共同作成者である場合は、ご自分の PR 内で記事の作成者を @ で言及し、サポートをご依頼ください。

<!--make sure to add this file to your includes folder and verify the path-->
[!INCLUDE [validation-reference-help](includes/validation-reference-help.md)]
