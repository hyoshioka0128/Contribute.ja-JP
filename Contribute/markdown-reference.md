---
title: docs.microsoft.com の Markdown 参照
description: Microsoft Docs プラットフォームで使われる Markdown の機能と構文について学習します。
author: meganbradley
ms.author: mbradley
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.openlocfilehash: b4ac631a4ebdf7daf00bc39be80fe2e479720392
ms.sourcegitcommit: 42e5a6ae071826afc2a32a9b7150ca113b39afdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "57987884"
---
# <a name="markdown-reference"></a><span data-ttu-id="eae4e-103">Markdown 参照</span><span class="sxs-lookup"><span data-stu-id="eae4e-103">Markdown Reference</span></span>

<span data-ttu-id="eae4e-104">Markdown は、プレーン テキスト形式の構文を使用する軽量のマークアップ言語です。</span><span class="sxs-lookup"><span data-stu-id="eae4e-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="eae4e-105">Docs プラットフォームでは、Markdown の CommonMark 標準がサポートされているほか、docs.microsoft.com で豊富なコンテンツを提供する目的で設計されたカスタム Markdown 拡張機能も一部サポートされています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-105">The Docs platform supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="eae4e-106">この記事では、docs.microsoft.com で Markdown を使用するためのアルファベット順参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-106">This article provides an alphabetical reference for using Markdown for docs.microsoft.com.</span></span>

<span data-ttu-id="eae4e-107">あらゆるテキスト エディターを使用して Markdown を作成できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="eae4e-108">標準の Markdown 構文とカスタム Docs 拡張機能の両方を簡単に挿入できるエディターとして、[Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) をインストールした [VS Code](https://code.visualstudio.com/) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eae4e-108">For an editor that facilitates inserting both standard Markdown syntax and custom Docs extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="eae4e-109">Docs では、Markdig Markdown エンジンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-109">Docs uses the Markdig Markdown engine.</span></span> <span data-ttu-id="eae4e-110">[https://babelmark.github.io/](https://babelmark.github.io/) では、Markdown のレンダリングを Markdig と他のエンジンで比較テストできます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="eae4e-111">アラート (注記、ヒント、重要、注意、警告)</span><span class="sxs-lookup"><span data-stu-id="eae4e-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="eae4e-112">アラートは Docs Markdown の拡張機能です。これにより、コンテンツの重要性を示す色とアイコンを使用して docs.microsoft.com 上でレンダリングされるブロック引用が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-112">Alerts are a Docs Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="eae4e-113">次の種類のアラートがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="eae4e-114">これらのアラートは docs.microsoft.com 上で次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="eae4e-115">Information the user should notice even if skimming. (ざっと読む場合でも、ユーザーは注意するべき情報。)</span><span class="sxs-lookup"><span data-stu-id="eae4e-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="eae4e-116">Optional information to help a user be more successful. (ユーザーにさらなる好結果を与える任意の情報。)</span><span class="sxs-lookup"><span data-stu-id="eae4e-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4e-117">Essential information required for user success. (ユーザーが好結果を得るために必須となる情報。)</span><span class="sxs-lookup"><span data-stu-id="eae4e-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="eae4e-118">Negative potential consequences of an action. (ある行動で起こりえる良くない結果。)</span><span class="sxs-lookup"><span data-stu-id="eae4e-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="eae4e-119">Dangerous certain consequences of an action. (ある行動で起こるいくつかの危険な結果。)</span><span class="sxs-lookup"><span data-stu-id="eae4e-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="eae4e-120">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="eae4e-120">Code snippets</span></span>

<span data-ttu-id="eae4e-121">Markdown ファイルにはコード スニペットを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="eae4e-122">見出し</span><span class="sxs-lookup"><span data-stu-id="eae4e-122">Headings</span></span>

<span data-ttu-id="eae4e-123">Docs では、6 つのレベルの Markdown 見出しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-123">Docs supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="eae4e-124">最後の `#` と見出しテキストの間にスペースを入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="eae4e-125">Markdown ファイルごとに与える H1 は 1 つだけにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="eae4e-126">H1 は YML メタデータ ブロックの後ろに来る、ファイルで最初のコンテンツにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="eae4e-127">H2 は右側に自動的に表示され、発行されたファイルのメニューのナビゲーションとなります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="eae4e-128">これより下のレベルの見出しは表示されません。そのため、閲覧者がコンテンツを移動する支えになるように H2 を戦略的に利用してください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="eae4e-129">`<h1>` など、HMTL 見出しは推奨されません。場合によっては、ビルド警告を発生させます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="eae4e-130">[ブックマーク](#bookmark-links)を利用し、ファイル内で個別の見出しにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="eae4e-131">HTML</span><span class="sxs-lookup"><span data-stu-id="eae4e-131">HTML</span></span>

<span data-ttu-id="eae4e-132">Markdown ではインライン HTML がサポートされていますが、Docs への公開には HTML は推奨されません。値の一覧が制限されていない限り、それによってビルドのエラーまたは警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-132">Although Markdown supports inline HTML, HTML is not recommended for publishing to Docs, and except for a limited list of values will cause build errors or warnings.</span></span>

## <a name="images"></a><span data-ttu-id="eae4e-133">イメージ</span><span class="sxs-lookup"><span data-stu-id="eae4e-133">Images</span></span>

<span data-ttu-id="eae4e-134">イメージをインクルードするための構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="eae4e-135">`alt text` はイメージの簡単な説明であり、`<folder path>` はイメージの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="eae4e-136">目が不自由な人のためにスクリーン リーダー用の代替テキストが必要になります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="eae4e-137">イメージをレンダリングできないサイト バグがある場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="eae4e-138">イメージはドキュメント セット内の `/media` フォルダーに格納してください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="eae4e-139">イメージには既定で次の種類のファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="eae4e-140">.jpg</span><span class="sxs-lookup"><span data-stu-id="eae4e-140">.jpg</span></span>
- <span data-ttu-id="eae4e-141">.png</span><span class="sxs-lookup"><span data-stu-id="eae4e-141">.png</span></span>

<span data-ttu-id="eae4e-142">ドキュメント セットの docfx.json ファイルにリソースとして追加することで、他の種類のイメージのサポートを追加できます</span><span class="sxs-lookup"><span data-stu-id="eae4e-142">You can add support for other image types by adding them as resources to the docfx.json file</span></span><!--add link to reference when available--> <span data-ttu-id="eae4e-143">。</span><span class="sxs-lookup"><span data-stu-id="eae4e-143">for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="eae4e-144">リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-144">Links</span></span>

<span data-ttu-id="eae4e-145">多くの場合、Docs では、他のファイルやページへの標準の Markdown リンクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-145">In most cases, Docs uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="eae4e-146">リンクの種類については、下のセクションに説明があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-146">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="eae4e-147">Docs Authoring Pack for VS Code を利用すれば、パスを理解する面倒な作業なく、相対的なリンクとブックマークを正しく挿入できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-147">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4e-148">Microsoft サイトへのリンクに en-us のようなロケール コードを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-148">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="eae4e-149">ハードコーディングされたロケール コードはローカライズされたコンテンツのレンダリングを妨げます。他のロケールのお客様に不自由を与えることになり、また、大きなローカライズ コストを発生させます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-149">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="eae4e-150">ブラウザーから URL をコピーすると、既定ではロケール コードが含まれます。そのため、リンクを作成するとき、手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-150">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete it when you create your link.</span></span> <span data-ttu-id="eae4e-151">たとえば、次のような URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-151">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="eae4e-152">次のような URL は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-152">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="eae4e-153">同じドキュメント セットのファイルの相対リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-153">Relative links to files in the same doc set</span></span>

<span data-ttu-id="eae4e-154">相対パスとは、現在のファイルから見た目的のファイルまでのパスです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-154">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="eae4e-155">Docs では、相対パスを使用することで、同じドキュメント セット内の別のファイルにリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-155">In Docs, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="eae4e-156">相対パスの構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-156">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="eae4e-157">`../` は階層で 1 つ上を示します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-157">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="eae4e-158">相対パスはビルド中に解決されますが、その中で .md 拡張が削除されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-158">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="eae4e-159">"../" を使用して親フォルダー内のファイルにリンクできますが、そのファイルは同じドキュメント セット内に置かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-159">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="eae4e-160">"../" を使用して別のドキュメント セット フォルダー内のファイルにリンクすることはできません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-160">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="eae4e-161">Docs では、"~" で始まる特殊な形式の相対パスもサポートされています (~/foo/bar.md など)。</span><span class="sxs-lookup"><span data-stu-id="eae4e-161">Docs also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="eae4e-162">この構文は、ドキュメント セットのルート フォルダーから相対的に見たファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-162">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="eae4e-163">この種類のパスも、ビルド中に検証および解決されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-163">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4e-164">相対パスにファイル拡張子を含めてください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-164">Include the file extension in the relative path.</span></span> <span data-ttu-id="eae4e-165">その相対パスの目的ファイルの存在がビルドで検証されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-165">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="eae4e-166">相対パスにファイル拡張子が含まれない場合、ビルドにより、リンクが壊れていると警告されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-166">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="eae4e-167">たとえば、次のような URL を使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-167">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="eae4e-168">次のような URL は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-168">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="site-relative-links-to-other-files-on-docs"></a><span data-ttu-id="eae4e-169">Docs 上の他のファイルへのサイト相対リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-169">Site relative links to other files on Docs</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="eae4e-170">ファイル拡張子 (.md) を含めません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-170">Do not include the file extension (.md).</span></span> <span data-ttu-id="eae4e-171">Azure "articles" ドキュメント セットの外から Linux 概要ファイルにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="eae4e-171">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="eae4e-172">外部サイトへのリンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-172">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="eae4e-173">別の Web ページへの URL ベースのリンク (https:// を含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="eae4e-173">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="eae4e-174">ブックマーク リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-174">Bookmark links</span></span>

<span data-ttu-id="eae4e-175">同じリポジトリにおける別ファイルの見出しへのブックマーク リンクは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-175">Bookmark link to a heading in another file in the same repo.</span></span> <span data-ttu-id="eae4e-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-176">For example:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="eae4e-177">現在のファイルにある見出しへのブックマーク リンクは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-177">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="eae4e-178">ハッシュ記号 `#` に見出しの単語を続けて使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-178">Use a hash mark `#` followed by the words of the heading.</span></span> <span data-ttu-id="eae4e-179">見出しテキストをリンク テキストに変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eae4e-179">To change the heading text into link text:</span></span>
- <span data-ttu-id="eae4e-180">すべて小文字を使用する</span><span class="sxs-lookup"><span data-stu-id="eae4e-180">Use all lowercase characters</span></span>
- <span data-ttu-id="eae4e-181">句読点を削除する</span><span class="sxs-lookup"><span data-stu-id="eae4e-181">Remove punctuation</span></span>
- <span data-ttu-id="eae4e-182">スペースをダッシュに置き換える</span><span class="sxs-lookup"><span data-stu-id="eae4e-182">Replace spaces with dashes</span></span>

<span data-ttu-id="eae4e-183">たとえば、見出しの名前が "2.2 Security concerns" の場合は、ブックマークのリンク テキストは "#22-security-concerns" になります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-183">For example, if the heading name is "2.2 Security concerns", then the bookmark link text will be "#22-security-concerns".</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="eae4e-184">明示的なアンカー リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-184">Explicit anchor links</span></span>

<span data-ttu-id="eae4e-185">`<a>` HTML タグを使用する明示的なアンカー リンクは、ハブ ページと待ち受けページを除き、**必須ではないか、推奨されません**。</span><span class="sxs-lookup"><span data-stu-id="eae4e-185">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="eae4e-186">一般的な Markdown ファイルでは、前述のブックマークを使用してください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-186">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="eae4e-187">ハブ ページと待ち受けページについては、アンカーを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-187">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="eae4e-188">`## <a id="AnchorText"> </a>Header text` または `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="eae4e-188">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="eae4e-189">明示的なアンカーにリンクするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-189">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="eae4e-190">XREF (相互参照) リンク</span><span class="sxs-lookup"><span data-stu-id="eae4e-190">XREF (cross reference) links</span></span>

<span data-ttu-id="eae4e-191">現在のドキュメント セットまたは他のドキュメント セットにある自動生成 API 参照ページにリンクするには、一意の ID (UID) を持つ XREF リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-191">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="eae4e-192">他のドキュメント セットにある API 参照ページを参照するには、`docfx.json` ファイルで `xrefService` 構成を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-192">To reference API reference pages in other doc sets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="eae4e-193">UID は、クラスとメンバーの完全修飾名に相当します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-193">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="eae4e-194">UID の後ろに \* を追加すると、リンクは固有の API ではなく、オーバーロードのページを表すようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-194">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="eae4e-195">たとえば、`List<T>.BinarySearch*` を使用すると、`List<T>.BinarySearch(T, IComparer<T>)` のような固有のオーバーロードにリンクする代わりに BinarySearch Method ページにリンクします。</span><span class="sxs-lookup"><span data-stu-id="eae4e-195">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="eae4e-196">次のいずれかの構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-196">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="eae4e-197">自動リンク: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="eae4e-197">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="eae4e-198">任意の `displayProperty` クエリ パラメーターにより、完全修飾のリンク テキストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-198">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="eae4e-199">既定では、リンク テキストに表示されるのはメンバー名または型名のみです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-199">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="eae4e-200">マークダウン リンク: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="eae4e-200">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="eae4e-201">表示されるリンク テキストをカスタマイズする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-201">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="eae4e-202">例:</span><span class="sxs-lookup"><span data-stu-id="eae4e-202">Examples:</span></span>

- <span data-ttu-id="eae4e-203">`<xref:System.String>` は "String" としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-203">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="eae4e-204">`<xref:System.String?displayProperty=nameWithType>` は "System.String" としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-204">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="eae4e-205">`[String class](xref:System.String)` は "String class" としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-205">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="eae4e-206">現在、UID を検索する簡単な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-206">Right now, there is no easy way to find the UIDs.</span></span> <!-- ? --><span data-ttu-id="eae4e-207">API の UID を検索する最善の方法は、リンクする API のページのソースを表示し、ms.assetid という値を検索することです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-207">The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="eae4e-208">個別のオーバーロードの値は、ソースには表示されません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-208">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="eae4e-209">将来的に、より優れたシステムを提供できるように取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-209">We're working on having a better system in the future.</span></span>

<span data-ttu-id="eae4e-210">UID に特殊文字 \`、\#、\* が含まれている場合、UID の値は、それぞれ `%60`、`%23`、`%2A` のように HTML エンコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-210">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="eae4e-211">かっこがエンコードされている場合もありますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-211">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="eae4e-212">例:</span><span class="sxs-lookup"><span data-stu-id="eae4e-212">Examples:</span></span>

- <span data-ttu-id="eae4e-213">System.Threading.Tasks.Task\`1 は、`System.Threading.Tasks.Task%601` になります</span><span class="sxs-lookup"><span data-stu-id="eae4e-213">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="eae4e-214">System.Exception.\#ctor は、`System.Exception.%23ctor` になります</span><span class="sxs-lookup"><span data-stu-id="eae4e-214">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="eae4e-215">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) は、`System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29` になります</span><span class="sxs-lookup"><span data-stu-id="eae4e-215">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="eae4e-216">リスト (番号付き、箇条書き、チェックリスト)</span><span class="sxs-lookup"><span data-stu-id="eae4e-216">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="eae4e-217">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="eae4e-217">Numbered list</span></span>

<span data-ttu-id="eae4e-218">番号付きリストを作成するには、すべての 1 を使用できます。これは公開されると、連続する一覧としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-218">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="eae4e-219">ソースを読みやすくするために、リストをインクリメントできます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-219">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="eae4e-220">入れ子になっているリストなど、リストには文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-220">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="eae4e-221">Docs に公開するとき、それらは正しくレンダリングされません。番号を使用する入れ子リストは、公開されると、小文字としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-221">They do not render correctly when published to Docs. Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="eae4e-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-222">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="eae4e-223">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-223">This renders as follows:</span></span>

1. <span data-ttu-id="eae4e-224">This is</span><span class="sxs-lookup"><span data-stu-id="eae4e-224">This is</span></span>
1. <span data-ttu-id="eae4e-225">a parent numbered list</span><span class="sxs-lookup"><span data-stu-id="eae4e-225">a parent numbered list</span></span>
   1. <span data-ttu-id="eae4e-226">and this is</span><span class="sxs-lookup"><span data-stu-id="eae4e-226">and this is</span></span>
   1. <span data-ttu-id="eae4e-227">a nested numbered list</span><span class="sxs-lookup"><span data-stu-id="eae4e-227">a nested numbered list</span></span>
1. <span data-ttu-id="eae4e-228">(fin)</span><span class="sxs-lookup"><span data-stu-id="eae4e-228">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="eae4e-229">箇条書き</span><span class="sxs-lookup"><span data-stu-id="eae4e-229">Bulleted list</span></span>

<span data-ttu-id="eae4e-230">箇条書きを作成するには、`-` の後ろにスペースを入れてから各行を続けます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-230">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="eae4e-231">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-231">This renders as follows:</span></span>

- <span data-ttu-id="eae4e-232">This is</span><span class="sxs-lookup"><span data-stu-id="eae4e-232">This is</span></span>
- <span data-ttu-id="eae4e-233">a parent bulleted list</span><span class="sxs-lookup"><span data-stu-id="eae4e-233">a parent bulleted list</span></span>
  - <span data-ttu-id="eae4e-234">and this is</span><span class="sxs-lookup"><span data-stu-id="eae4e-234">and this is</span></span>
  - <span data-ttu-id="eae4e-235">a nested bulleted list</span><span class="sxs-lookup"><span data-stu-id="eae4e-235">a nested bulleted list</span></span>
- <span data-ttu-id="eae4e-236">All done!</span><span class="sxs-lookup"><span data-stu-id="eae4e-236">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="eae4e-237">チェックリスト</span><span class="sxs-lookup"><span data-stu-id="eae4e-237">Checklist</span></span>

<span data-ttu-id="eae4e-238">チェックリストは、カスタム Markdown 拡張経由で docs.microsoft.com (のみ) で使用する場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-238">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="eae4e-239">このサンプルは docs.microsoft.com で次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-239">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="eae4e-240">List item 1</span><span class="sxs-lookup"><span data-stu-id="eae4e-240">List item 1</span></span>
> * <span data-ttu-id="eae4e-241">List item 2</span><span class="sxs-lookup"><span data-stu-id="eae4e-241">List item 2</span></span>
> * <span data-ttu-id="eae4e-242">List item 3</span><span class="sxs-lookup"><span data-stu-id="eae4e-242">List item 3</span></span>

<span data-ttu-id="eae4e-243">"これから学習する内容" や "今回学習した内容" をまとめる目的で、記事の冒頭や最後でチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-243">Use checklists at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="eae4e-244">記事全体でランダムなチェックリストを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-244">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="eae4e-245">次のステップ アクション</span><span class="sxs-lookup"><span data-stu-id="eae4e-245">Next step action</span></span>

<span data-ttu-id="eae4e-246">カスタム拡張を使用し、次のステップ アクション ボタンを docs.microsoft.com (のみ) のページに追加できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-246">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="eae4e-247">構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-247">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="eae4e-248">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-248">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="eae4e-249">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-249">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="eae4e-250">Learn about basic style</span><span class="sxs-lookup"><span data-stu-id="eae4e-250">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="eae4e-251">別の Web ページへの Markdown リンクを含め、次のステップ アクションでは、サポートされているあらゆるリンクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-251">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="eae4e-252">ほとんどの場合、次のアクション リンクは同じドキュメント セット内の別のファイルへの相対リンクになります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-252">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="eae4e-253">セクション定義</span><span class="sxs-lookup"><span data-stu-id="eae4e-253">Section definition</span></span>

<!-- more info about this would be helpful! -->
<span data-ttu-id="eae4e-254">セクションを定義する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-254">You might need to define a section.</span></span> <span data-ttu-id="eae4e-255">この構文は多くの場合、コード表に使用されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-255">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="eae4e-256">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-256">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="eae4e-257">前述のブロック引用 Markdown テキストは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-257">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="eae4e-258">セレクター</span><span class="sxs-lookup"><span data-stu-id="eae4e-258">Selectors</span></span>

<!-- could be more clear! -->
<span data-ttu-id="eae4e-259">同じ記事に対してさまざまなページをつなげる場合は、セレクターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-259">You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="eae4e-260">閲覧者はページを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-260">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="eae4e-261">この拡張機能は、docs.microsoft.com と MSDN で機能が異なります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-261">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="eae4e-262">単一セレクター</span><span class="sxs-lookup"><span data-stu-id="eae4e-262">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="eae4e-263">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-263">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="eae4e-272">複数のセレクター</span><span class="sxs-lookup"><span data-stu-id="eae4e-272">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="eae4e-273">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-273">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)

## <a name="tables"></a><span data-ttu-id="eae4e-284">表</span><span class="sxs-lookup"><span data-stu-id="eae4e-284">Tables</span></span>

<span data-ttu-id="eae4e-285">Markdow で表を作成する最も簡単な方法は、パイプと行を使用することです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-285">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="eae4e-286">ヘッダー付きの標準的な表を作成するには、最初の行の後に点線を続けます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-286">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="eae4e-287">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-287">This renders as follows:</span></span>

|<span data-ttu-id="eae4e-288">This is</span><span class="sxs-lookup"><span data-stu-id="eae4e-288">This is</span></span>   |<span data-ttu-id="eae4e-289">a simple</span><span class="sxs-lookup"><span data-stu-id="eae4e-289">a simple</span></span>   |<span data-ttu-id="eae4e-290">table header</span><span class="sxs-lookup"><span data-stu-id="eae4e-290">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="eae4e-291">table</span><span class="sxs-lookup"><span data-stu-id="eae4e-291">table</span></span>     |<span data-ttu-id="eae4e-292">data</span><span class="sxs-lookup"><span data-stu-id="eae4e-292">data</span></span>       |<span data-ttu-id="eae4e-293">here</span><span class="sxs-lookup"><span data-stu-id="eae4e-293">here</span></span>        |
|<span data-ttu-id="eae4e-294">it doesn't</span><span class="sxs-lookup"><span data-stu-id="eae4e-294">it doesn't</span></span>|<span data-ttu-id="eae4e-295">actually</span><span class="sxs-lookup"><span data-stu-id="eae4e-295">actually</span></span>   |<span data-ttu-id="eae4e-296">have to line up nicely!</span><span class="sxs-lookup"><span data-stu-id="eae4e-296">have to line up nicely!</span></span>||

<span data-ttu-id="eae4e-297">ヘッダーなしで表を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-297">You can also create a table without a header.</span></span> <span data-ttu-id="eae4e-298">たとえば、複数列のリストを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eae4e-298">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="eae4e-299">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-299">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="eae4e-300">This</span><span class="sxs-lookup"><span data-stu-id="eae4e-300">This</span></span> | <span data-ttu-id="eae4e-301">table</span><span class="sxs-lookup"><span data-stu-id="eae4e-301">table</span></span> |
| <span data-ttu-id="eae4e-302">has no</span><span class="sxs-lookup"><span data-stu-id="eae4e-302">has no</span></span> | <span data-ttu-id="eae4e-303">header</span><span class="sxs-lookup"><span data-stu-id="eae4e-303">header</span></span> |

<span data-ttu-id="eae4e-304">コロンを使用して、列を整列することができます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-304">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="eae4e-305">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-305">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="eae4e-306">right aligned:</span><span class="sxs-lookup"><span data-stu-id="eae4e-306">right aligned:</span></span>|
|<span data-ttu-id="eae4e-307">:left aligned</span><span class="sxs-lookup"><span data-stu-id="eae4e-307">:left aligned</span></span>     |
|<span data-ttu-id="eae4e-308">:centered        :</span><span class="sxs-lookup"><span data-stu-id="eae4e-308">:centered        :</span></span>|

> [!TIP]
> Docs Authoring Extension for VS Code では、基本的な Markdown 表を簡単に追加できます。
>
> [オンラインの表生成機能](http://www.tablesgenerator.com/markdown_tables)を使用することもできます。

### <a name="mx-tdbreakall"></a><span data-ttu-id="eae4e-311">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="eae4e-311">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> これは docs.microsoft.com サイトでのみ機能します。

<span data-ttu-id="eae4e-313">Markdown で表を作成すると、表が右側のナビゲーションまで広がって、表が読めなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-313">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="eae4e-314">これは、必要に応じて、Docs のレンダリングで表内の改行を許可することで解決できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-314">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="eae4e-315">カスタム クラス `[!div class="mx-tdBreakAll"]` を使用して表を折り返すだけです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-315">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="eae4e-316">クラス名が `mx-tdBreakAll` の `div` で折り返される 3 行の表の Markdown サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-316">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="eae4e-317">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-317">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="eae4e-318">名前</span><span class="sxs-lookup"><span data-stu-id="eae4e-318">Name</span></span>|<span data-ttu-id="eae4e-319">構文</span><span class="sxs-lookup"><span data-stu-id="eae4e-319">Syntax</span></span>|<span data-ttu-id="eae4e-320">サイレント インストールでは必須ですか。</span><span class="sxs-lookup"><span data-stu-id="eae4e-320">Mandatory for silent installation?</span></span>|<span data-ttu-id="eae4e-321">Description</span><span class="sxs-lookup"><span data-stu-id="eae4e-321">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="eae4e-322">Quiet</span><span class="sxs-lookup"><span data-stu-id="eae4e-322">Quiet</span></span>|<span data-ttu-id="eae4e-323">/quiet</span><span class="sxs-lookup"><span data-stu-id="eae4e-323">/quiet</span></span>|<span data-ttu-id="eae4e-324">Yes</span><span class="sxs-lookup"><span data-stu-id="eae4e-324">Yes</span></span>|<span data-ttu-id="eae4e-325">Runs the installer, displaying no UI and no prompts.</span><span class="sxs-lookup"><span data-stu-id="eae4e-325">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="eae4e-326">NoRestart</span><span class="sxs-lookup"><span data-stu-id="eae4e-326">NoRestart</span></span>|<span data-ttu-id="eae4e-327">/norestart</span><span class="sxs-lookup"><span data-stu-id="eae4e-327">/norestart</span></span>|<span data-ttu-id="eae4e-328">No</span><span class="sxs-lookup"><span data-stu-id="eae4e-328">No</span></span>|<span data-ttu-id="eae4e-329">Suppresses any attempts to restart.</span><span class="sxs-lookup"><span data-stu-id="eae4e-329">Suppresses any attempts to restart.</span></span> <span data-ttu-id="eae4e-330">By default, the UI will prompt before restart.</span><span class="sxs-lookup"><span data-stu-id="eae4e-330">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="eae4e-331">Help</span><span class="sxs-lookup"><span data-stu-id="eae4e-331">Help</span></span>|<span data-ttu-id="eae4e-332">/help</span><span class="sxs-lookup"><span data-stu-id="eae4e-332">/help</span></span>|<span data-ttu-id="eae4e-333">No</span><span class="sxs-lookup"><span data-stu-id="eae4e-333">No</span></span>|<span data-ttu-id="eae4e-334">Provides help and quick reference.</span><span class="sxs-lookup"><span data-stu-id="eae4e-334">Provides help and quick reference.</span></span> <span data-ttu-id="eae4e-335">Displays the correct use of the setup command, including a list of all options and behaviors.</span><span class="sxs-lookup"><span data-stu-id="eae4e-335">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="eae4e-336">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="eae4e-336">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae4e-337">これは docs.microsoft.com サイトでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-337">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="eae4e-338">ときどき、表の 2 番目の列に非常に長い単語がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-338">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="eae4e-339">そのような単語を適切に分割するために、前述のような `div` ラッパー構文を使用して `mx-tdCol2BreakAll` クラスを適用できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-339">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="eae4e-340">HTML テーブル</span><span class="sxs-lookup"><span data-stu-id="eae4e-340">HTML Tables</span></span>

<span data-ttu-id="eae4e-341">docs.microsoft.com の場合、HTML テーブルは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="eae4e-341">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="eae4e-342">ソースでは人間が読めないようになっています。このことは Markdown の重要な原則の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="eae4e-342">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="eae4e-343">動画</span><span class="sxs-lookup"><span data-stu-id="eae4e-343">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="eae4e-344">Markdown ページに動画を埋め込む</span><span class="sxs-lookup"><span data-stu-id="eae4e-344">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="eae4e-345">現在、Docs では、次の 3 つの場所のいずれかに公開される動画がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-345">Currently, Docs can support videos published to one of three locations:</span></span>

- <span data-ttu-id="eae4e-346">YouTube</span><span class="sxs-lookup"><span data-stu-id="eae4e-346">YouTube</span></span>
- <span data-ttu-id="eae4e-347">Channel 9</span><span class="sxs-lookup"><span data-stu-id="eae4e-347">Channel 9</span></span>
- <span data-ttu-id="eae4e-348">Microsoft 独自の 'One Player' システム</span><span class="sxs-lookup"><span data-stu-id="eae4e-348">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="eae4e-349">次の構文を使用してビデオを埋め込むことができ、そのビデオは Docs でレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-349">You can embed a video with the following syntax, and Docs will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="eae4e-350">例:</span><span class="sxs-lookup"><span data-stu-id="eae4e-350">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="eae4e-351">これは次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-351">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="eae4e-352">公開されたページでは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-352">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="eae4e-353">CH9 ビデオの URL は `https` で始まり、`/player` で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae4e-353">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="eae4e-354">そうしないと、ビデオだけでなくページ全体が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-354">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="eae4e-355">新しい動画をアップロードする</span><span class="sxs-lookup"><span data-stu-id="eae4e-355">Uploading new videos</span></span>

<span data-ttu-id="eae4e-356">新しい動画は次のプロセスでアップロードしてください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-356">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="eae4e-357">IDWEB で **docs_video_users** グループに参加します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-357">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="eae4e-358">[https://aka.ms/VideoUploadRequest](https://aka.ms/VideoUploadRequest ) に移動し、動画の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-358">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="eae4e-359">次の項目が必要になります (いずれも公開されません)。</span><span class="sxs-lookup"><span data-stu-id="eae4e-359">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="eae4e-360">動画のタイトル。</span><span class="sxs-lookup"><span data-stu-id="eae4e-360">A title for your video.</span></span>
    1. <span data-ttu-id="eae4e-361">動画が関連する製品/サービスの一覧。</span><span class="sxs-lookup"><span data-stu-id="eae4e-361">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="eae4e-362">動画がホストされる対象ページまたは (ページをまだ用意していない場合) ドキュメント セット。</span><span class="sxs-lookup"><span data-stu-id="eae4e-362">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="eae4e-363">動画の MP4 ファイルへのリンク (ファイルを置く場所を用意していない場合、`\\scratch2\scratch\apex` に一時的に置くことができます)。</span><span class="sxs-lookup"><span data-stu-id="eae4e-363">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="eae4e-364">MP4 ファイルは 720p 以上にしてください。</span><span class="sxs-lookup"><span data-stu-id="eae4e-364">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="eae4e-365">動画の説明。</span><span class="sxs-lookup"><span data-stu-id="eae4e-365">A description of the video.</span></span>
1. <span data-ttu-id="eae4e-366">項目を送信 (保存) します。</span><span class="sxs-lookup"><span data-stu-id="eae4e-366">Submit (save) that item.</span></span>
1. <span data-ttu-id="eae4e-367">2 営業日以内に動画がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-367">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="eae4e-368">埋め込みに必要なリンクは作業項目に配置されます。解決されて*戻されます*。</span><span class="sxs-lookup"><span data-stu-id="eae4e-368">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="eae4e-369">動画リンクを取得したら、作業項目を閉じます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-369">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="eae4e-370">その後、次の構文を利用し、動画リンクを投稿に追加できます。</span><span class="sxs-lookup"><span data-stu-id="eae4e-370">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
