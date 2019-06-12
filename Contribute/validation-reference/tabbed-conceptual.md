---
ms.date: 03/29/2019
title: タブ付き概念
ms.openlocfilehash: 3d6f38c1659297182a8bd50bf52b9853bd21b2c8
ms.sourcegitcommit: 1e53d17639277bebd89b2e7cabeb45bdad526354
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "66841286"
---
# <a name="tabbed-conceptual"></a><span data-ttu-id="33ef1-102">タブ付き概念</span><span class="sxs-lookup"><span data-stu-id="33ef1-102">Tabbed conceptual</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33ef1-103">タブ付き概念図の構文は非推奨となっているため、新しいタブを追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="33ef1-103">The tabbed conceptual syntax has been deprecated and new tabs should not be added.</span></span> <span data-ttu-id="33ef1-104">この記事で説明する検証は、代わりとなる機能が使用できるようになるまでタブ付き概念図の使用が認められているコンテンツ セットに適用されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-104">The validations described in this article apply to content sets that have been approved to use tabbed conceptual until replacement functionality is available.</span></span>

## <a name="tab-syntax"></a><span data-ttu-id="33ef1-105">タブ構文</span><span class="sxs-lookup"><span data-stu-id="33ef1-105">Tab syntax</span></span>

<span data-ttu-id="33ef1-106">タブの構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-106">The syntax for tabs is as follows:</span></span>

<span data-ttu-id="33ef1-107">単一レベルのタブ:</span><span class="sxs-lookup"><span data-stu-id="33ef1-107">Single level tab:</span></span>

`# [Tab Display Name](#tab/tab-id)`

<span data-ttu-id="33ef1-108">省略可能な依存タブ:</span><span class="sxs-lookup"><span data-stu-id="33ef1-108">Optional dependent tab:</span></span>

`# [Tab Display Name](#tab/tab-id/tab-condition)`

<span data-ttu-id="33ef1-109">2 つのタブとタブ グループ終端記号を含む単一レベルのタブ セクションの例:</span><span class="sxs-lookup"><span data-stu-id="33ef1-109">Example of a single-level tab section with two tabs and the tab group terminator (---):</span></span>

```markdown
# [Linux](#tab/linux)

Content for Linux...

# [Windows](#tab/windows)

Content for Windows...

---
```

<span data-ttu-id="33ef1-110">タブには、必要に応じてセカンダリ タブまたは依存関係タブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-110">Tabs can optionally contain secondary tabs, or dependency tabs.</span></span> <span data-ttu-id="33ef1-111">これにより、タブは別のタブ セットでの選択に依存するようになります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-111">This makes tabs dependent on the selection in another set of tabs.</span></span> <span data-ttu-id="33ef1-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="33ef1-112">Here's an example:</span></span>

```markdown
# [Azure CLI](#tab/azure-cli/linux)

Azure CLI content for Linux...

# [Azure CLI](#tab/azure-cli/windows)

Azure CLI content for Windows...

# [PowerShell](#tab/azure-powershell/linux)

PowerShell content for Linux...

# [PowerShell](#tab/azure-powershell/windows)

PowerShell content for Windows...

---
```

<span data-ttu-id="33ef1-113">タブ構文には次の検証が適用されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-113">The following validations apply to tab syntax:</span></span>

- <span data-ttu-id="33ef1-114">タブ構文が正しくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="33ef1-114">Tab syntax must be correct.</span></span>
- <span data-ttu-id="33ef1-115">依存タブは、前のタブ グループ内で定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-115">Dependent tabs must have been defined in a previous tab group.</span></span>
- <span data-ttu-id="33ef1-116">許可される依存関係は単一レベルに限られます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-116">Only one level of dependency is allowed.</span></span>
- <span data-ttu-id="33ef1-117">2 つ以上のタブが許可されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-117">No fewer than two tabs are allowed.</span></span>
- <span data-ttu-id="33ef1-118">4 つ以下のタブが許可されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-118">No more than four tabs are allowed.</span></span>
- <span data-ttu-id="33ef1-119">タブは許可される必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-119">Tabs must be approved.</span></span>
- <span data-ttu-id="33ef1-120">タブ/ID のペアが有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-120">Tab/ID pairs must be valid.</span></span>
- <span data-ttu-id="33ef1-121">1 つのタブ グループ内で同じタブ ID を複数回使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="33ef1-121">Cannot have the same tab ID multiple times in one tab group.</span></span>

## <a name="approved-tabs"></a><span data-ttu-id="33ef1-122">承認されているタブ</span><span class="sxs-lookup"><span data-stu-id="33ef1-122">Approved tabs</span></span>

<span data-ttu-id="33ef1-123">次のタブ名/タブ ID のペアが許可されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-123">The following tab name/tab ID pairs are approved.</span></span> <span data-ttu-id="33ef1-124">依存タブ ID は、ペアになりませんが、タブ ID 列ごとに有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ef1-124">Dependent tab IDs are not paired but must be valid per the Tab ID column.</span></span> <span data-ttu-id="33ef1-125">値は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="33ef1-125">The values are case-sensitive</span></span>

|<span data-ttu-id="33ef1-126">タブ名</span><span class="sxs-lookup"><span data-stu-id="33ef1-126">Tab name</span></span>              |<span data-ttu-id="33ef1-127">タブ ID</span><span class="sxs-lookup"><span data-stu-id="33ef1-127">Tab ID</span></span>            |
|----------------------|------------------|
|`[.NET]`              |`(#tab/dotnet)`   |
|`[.NET Core 1.x]`     |`(#tab/netcore1x)`|
|`[.NET Core 2.x]`     |`(#tab/netcore2x)`|
|`[.NET Core 2.0]`     |`(#tab/netcore20)`|
|`[.NET Core 2.1]`     |`(#tab/netcore21)`|
|`[.NET Core 2.2]`     |`(#tab/netcore22)`|
|`[.NET Core 3.x]`     |`(#tab/netcore3x)`|
|`[.NET Core 3.0]`     |`(#tab/netcore30)`|
|`[.NET Core CLI]`     |`(#tab/netcore-cli)`|
|`[Azure CLI]`         |`(#tab/azure-cli)`|
|`[Android]`           |`(#tab/android)`  |
|`[Browser]`           |`(#tab/browser)`  |
|`[C#]`                |`(#tab/csharp)`   |
|`[C# Script]`         |`(#tab/csharp-script)`|
|`[CentOS]`            |`(#tab/centos)`|
|`[Command Line]`      |`(#tab/command-line)`|
|`[Debian]`            |`(#tab/debian)`|
|`[Docker Hub]`        |`(#tab/docker-hub)`|
|`[F#]`                |`(#tab/fsharp)`|
|`[Fedora]`            |`(#tab/fedora)`|
|`[iOS]`               |`(#tab/ios)`      |
|`[Java]`              |`(#tab/java)`|
|`[JavaScript]`        |`(#tab/javascript)`|
|`[Linux]`             |`(#tab/linux)`    |
|`[macOS]`             |`(#tab/macos)`    |
|`[Managed Kubernetes]`|`(#tab/kubernetes-managed)`|
|`[Maven]`             |`(#tab/maven)`|
|`[Mint]`              |`(#tab/mint)`|
|`[Node.js]`           |`(#tab/nodejs)`|
|`[npm]`               |`(#tab/npm)` |
|`[NuGet]`             |`(#tab/nuget)`|
|`[openSUSE]`          |`(#tab/opensuse)`|
|`[Other]`             |`(#tab/other)` |
|`[Oracle Linux]`      |`(#tab/oracle-linux)`|
|`[Package Manager]`   |`(#tab/package-manager)` |
|`[PEAR]`              |`(#tab/pear)`|
|`[pip]`               |`(#tab/pip)`|
|`[Portal]`            |`(#tab/azure-portal)`    |
|`[PowerShell]`        |`(#tab/azure-powershell)`|
|`[Private Registry]`  |`(#tab/private-registry)`|
|`[Python]`            |`(#tab/python)`|
|`[Resource Manager Template]`|`(#tab/azure-resource-manager)`|
|`[RHEL]`              |`(#tab/rhel)`|
|`[RubyGems]`          |`(#tab/rubygems)`|
|`[SQL Server]`        |`(#tab/sql-server)`|
|`[SQLite]`            |`(#tab/sqlite)`|
|`[TypeScript]`        |`(#tab/typescript)`|
|`[Visual Basic]`      |`(#tab/vb)` |
|`[Visual Studio]`     |`(#tab/visual-studio)`|
|`[Visual Studio 15.6 and earlier]`|`(#tab/vs156)`|
|`[Visual Studio 15.7 and later]`  |`(#tab/vs157)`|
|`[Visual Studio Code]`            |`(#tab/visual-studio-code)`|
|`[Visual Studio for Mac]`         |`(#tab/visual-studio-mac)`|
|`[Ubuntu]`                        |`(#tab/ubuntu)`|
|`[Unmanaged Kubernetes]`          |`(#tab/kubernetes-unmanaged)`|
|`[Windows]`   |`(#tab/windows)`   |