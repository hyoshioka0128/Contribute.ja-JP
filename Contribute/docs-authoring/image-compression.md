---
title: 画像の圧縮 - Docs Authoring Pack
description: Visual Studio Code 拡張機能の Docs Authoring Pack 内で画像を圧縮する方法について説明します。
author: IEvangelist
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.date: 03/03/2020
ms.author: dapine
ms.openlocfilehash: 4b93ac23b83128d5b9125297879d008e9300509c
ms.sourcegitcommit: cfba5ad25b898bfed76046126ce8ff4871910701
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "78336660"
---
# <a name="image-compression"></a>画像の圧縮

[!INCLUDE [markdown-extension](includes/image-extension.md)]

## <a name="summary"></a>サマリー

docs の PDF バージョンを除いて、すべてのドキュメントは Web 経由で提供されます。静的コンテンツを提供する場合、ネットワーク経由で送信されるバイト数を最小限に抑えることをお勧めします。 そのための 1 つの方法として、保存時の画像の圧縮があります。

Docs Authoring Pack 拡張機能には、画像の圧縮コンテキスト メニュー項目が含まれています。 サポートされる画像の種類と拡張子は、次のとおりです。

* "*\*.png*"
* "*\*.jpg*"
* "*\*.jpeg*"
* "*\*.gif*"
* "*\*.svg*"
* "*\*.webp*"

必要に応じて、画像の無損失圧縮アルゴリズムを使用します。

## <a name="compress-image"></a>画像を圧縮

**エクスプローラー**のナビゲーション ウィンドウで、画像ファイルを右クリックし、**[Compress image]\(画像を圧縮する\)** オプションを選択します。 画像が圧縮されます。

## <a name="compress-images-in-folder"></a>フォルダー内の画像を圧縮

**エクスプローラー**のナビゲーション ウィンドウで、画像ファイルを右クリックし、**[Compress images in folder]\(フォルダー内の画像を圧縮する\)** オプションを選択します。 フォルダー内のすべての画像が圧縮されます。

## <a name="considerations"></a>考慮事項

高解像度の画像は暗黙的にサイズが変更されます。 最大寸法は、プラットフォームで推奨される最大幅の `1,200px` に基づきます。 最大値は、画像が推奨されるサイズよりも大きい場合にのみ使用され、自動的にサイズ変更される場合、それらの縦横比は維持されます。

## <a name="preferences"></a>基本設定

最大寸法は構成可能ですが、既定の最大幅は `1200` ピクセルです。 最大寸法を構成するには、**[ファイル]、[基本設定]、[設定]** の順に選択し、`"Docs Image Extension"` でフィルター処理します。

:::image type="content" source="media/configure-image-compression.png" alt-text="画像の圧縮の構成":::

> [!NOTE]
> **[幅の最大値]** または **[高さの最大値]** の値が `0` の場合、解像度の差異が無視されるだけです。

## <a name="in-action"></a>操作の実例

この機能の簡単なデモンストレーションを以下に示します。

[![画像の圧縮のデモ](media/compress-image.gif)](media/compress-image.gif#lightbox)
