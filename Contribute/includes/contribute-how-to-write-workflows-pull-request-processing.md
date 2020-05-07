---
ms.openlocfilehash: 9cb0ba651d40d2834081d32443a8fd2b1152003d
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "53286218"
---
## <a name="pull-request-processing"></a>Pull request の処理

前のセクションでは、変更提案を新しい pull request (PR) にバンドルし、宛先リポジトリの PR キューに追加するという変更提案の提出プロセスを確認しました。 Pull request は、自分の作業ブランチの変更内容をプルし、別のブランチにマージするように求めることで、GitHub のコラボレーション モデルを可能にします。 ほとんどの場合、このもう 1 つのブランチは、メイン リポジトリの default/master ブランチです。

### <a name="validation"></a>検証

Pull request が対象のブランチにマージされるには、1 つ以上の PR 検証プロセスを経る必要がある場合があります。 検証プロセスは、変更提案の範囲と、宛先リポジトリの規則に応じて異なる場合があります。 Pull request の提出後、次のような動作が想定されます。

- **マージ機能**: 基本的な GitHub のマージ機能テストが最初に行われます。これにより、ご自分のブランチでの変更提案が宛先ブランチと競合しないかが検証されます。 このテストで不合格になったと pull request に表示された場合、処理を続行する前に、マージ競合の原因となっているコンテンツを調整する必要があります。
- **CLA**: パブリック リポジトリに投稿しているが、Microsoft の社員ではない場合、変更提案の重要性によっては、pull request をそのリポジトリに初めて送信したときに簡単な貢献者使用許諾契約書 (CLA) に記入するように求められることがあります。 CLA の手続きが終わると、pull request が処理されます。
- **ラベル付け**: pull request にはラベルが自動的に適用されます。これにより、pull request が検証ワークフローを通過したとき、その状態が示されます。 たとえば、新しい pull requests に "do-not-merge" ラベルが自動的に付けられることがあります。これは、その pull request が検証、レビュー、サインオフの手続きを完了していないことを示します。
- **検証とビルド**: 自動化されたチェックにより、変更内容が検証テストに合格するかどうかが確認されます。 検証テストの結果、警告やエラーが表示され、pull request の 1 つまたは複数のファイルを変更するように求められることがあります。変更しないと、マージできません。 検証テストの結果は、見直せるようにコメントとして pull request に追加されます。メールで送信される場合もあります。
- **ステージング**: ご自分の変更によって影響を受ける記事ページは、検証およびビルドが正常に行われたかを確認するために、自動的にステージング環境に配置されます。 PR コメントにプレビュー URL が表示されます。
- **自動マージ**: 検証テストと特定の基準に合格すると、pull request が自動的にマージされることがあります。 この場合、それ以上何らかの操作を行う必要はありません。

### <a name="review-and-sign-off"></a>レビューとサインオフ

すべての PR 処理が完了したら、結果を見直し (PR コメントやプレビュー URL など)、マージをサインオフする前に、追加の変更がそのファイルに必要かどうかを判断してください。 Pull request が PR レビュー担当者によって見直されている場合、マージ前に解決するべき大きな問題があれば、レビュー担当者はコメントを介してフィードバックを提供することもできます。

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Pull request に問題がなく、サインオフされたら、変更提案は親ブランチにマージされ、pull request が終了となります。

### <a name="publishing"></a>発行

変更を次に予定されている発行に含めるには、PR のレビュー担当者が pull request をマージする必要があります。 Pull request は通常、提出順でレビュー、およびマージされます。 Pull request を特定の発行でマージする必要がある場合、発行前にマージするために、早めに PR レビュー担当者と協力する必要があります。

投稿が承認され、マージされると、docs.microsoft.com の発行プロセスに追加されます。 投稿先のリポジトリを管理するチームによって発行時間が異なります。 次のパスで発行された記事は通常、月曜日から金曜日までの午前 10 時 30 分頃 (太平洋時間の午後 3 時 30 分頃) にデプロイされます。

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

発行後、記事がオンライン表示されるまで最大 45 分かかります。 記事の公開後、自分の変更提案を URL (`https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`) で確認できます。
