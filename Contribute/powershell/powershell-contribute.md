---
title: PowerShell ドキュメント リポジトリに協力する
description: PowerShell ドキュメントを構成するリポジトリの記事。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: sdwheeler
ms.author: sewhee
ms.date: 10/09/2019
ms.openlocfilehash: 6b975c085aa42846be9951a77d3fdebbd5fb17a1
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72290175"
---
# <a name="contributing-to-powershell-documentation"></a>PowerShell ドキュメントへの協力

PowerShell ドキュメントに関心をお寄せいただきありがとうございます。

このドキュメントでは、PowerShell ドキュメント サイトに掲載される記事やコード サンプルに協力する過程について取り上げています。 協力には誤植の修正のような単純なものから、新しい記事のような入り組んだものまであります。

PowerShell ドキュメント サイトは、1 つ以上の docset を含む複数のリポジトリから構築されています。

- [PowerShell の概念とコマンドレット リファレンス][psdocs]
- PowerShell SDK コード サンプル - SDK の記事で使用されているサンプルを含むプライベート リポジトリ
- [PowerShell .NET SDK リファレンス](/dotnet/api/?view=pscore-6.2.0) - PowerShell ソース コードから生成されたプライベート リポジトリ コンテンツ

これらすべてのコンテンツのイシューは、[PowerShell-Docs][docsrepo] リポジトリで追跡されます。

## <a name="repository-structure"></a>リポジトリの構造

PowerShell-Docs リポジトリは、[Microsoft Docs][psdocs] に発行される 3 つの docset で構成されます。docset は、次のフォルダーに含まれています。

- [/reference/][ref] - PowerShell に付属するコマンドレットの PowerShell コマンドレット リファレンスが含まれています。 リファレンスは、バージョンのフォルダー (3.0、4.0、5.0、5.1、6、および 7) にまとめられています。 この docset には、Windows またはその他の Microsoft 製品に付属するモジュールのリファレンスは含まれていません。
- [/reference/docs-conceptual][conceptual] - PowerShell の概念説明ドキュメントが含まれています。 これには、セットアップ手順、サンプル スクリプト、操作方法に関するトピックなどが含まれます。
- [/developer/][SDK] - PowerShell SDK の概念説明ドキュメントが含まれています。

<!--link refs-->
[psdocs]: https://docs.microsoft.com/powershell
[docsrepo]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[SDK]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/developer
