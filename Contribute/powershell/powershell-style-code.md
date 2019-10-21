---
title: スクリプト サンプルの作成に関する具体的なガイダンス
description: この記事では、PowerShell コード サンプルの書式設定に関する具体的な規則について説明します。 これは、例が含まれる概念記事や、コマンドレット リファレンスに適用されます。
ms.topic: contributor-guide
ms.prod: non-product-specific
ms.custom: external-contributor-guide
author: sdwheeler
ms.author: sewhee
ms.date: 10/09/2019
ms.openlocfilehash: f036ece21d139df0be1d677dc536023910c9d20b
ms.sourcegitcommit: ca84e542b081e145052f38967e826f6ef25da1b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72290267"
---
# <a name="formatting-code-samples"></a>コード サンプルの書式設定

既存のドキュメントには、時間の経過と共に複数のスタイルが使用され、書式設定規則は複数回変更されています。 PowerShell コード ブロックとドキュメントの出力については一貫したスタイルを確立しようと取り組んでいます。

Markdown は、次の 2 つの異なるコード スタイルをサポートしています。

- コード スパン (インライン) - 1 つのバッククォート (`` ` ``) 文字でマークされます。 スタンドアロン ブロックとしてではなく、段落内のインラインで使用されます。 コマンドレット名を囲む場合によく使用されます。 「[コマンド構文要素の書式設定](powershell-style-basic-markdown.md#formatting-command-syntax-elements)」を参照してください。
- コード ブロック - トリプルバッククォート (`` ``` ``) 文字列で囲まれた複数行のブロック。

## <a name="using-code-blocks"></a>コード ブロックの使用

Markdown では、インデントでコード ブロックを指定できますが、このパターンは問題になる可能性があるため、回避するようにします。 すべてのコード ブロックは、コード フェンス内に含めるようにします。 コード フェンスは、トリプルバッククォート (`` ``` ``) 文字列で囲まれたコードのブロックです。 コード フェンス マーカーは、コード サンプルの前後にある独自の行に配置する必要があります。 コード ブロックの先頭にあるマーカーには、省略可能な言語ラベルを含めることができます。 Microsoft の Open Publishing System (OPS) では、言語ラベルを使用して、構文の強調表示機能をサポートしています。

また、OPS では、コード ブロックの内容をクリップボードにコピーする **[コピー]** ボタンも追加されます。 これにより、コード例をテストするスクリプトにコードを迅速に貼り付けることができます。 ただし、ドキュメントのすべての例がそのように実行されることを意図しているわけではありません。 一部のコード ブロックは、PowerShell の概念の単純な図や、構文の抽象的な表現である場合があります。

ドキュメントには、次の 2 種類のコード ブロックが使用されています。

1. わかりやすい例
2. 実行可能ファイルの例

## <a name="formatting-illustrative-examples"></a>わかりやすい例の書式設定

わかりやすい例は、PowerShell の概念を説明するために使用されます。 実行のためにクリップボードにコピーするためのものではありません。 これらは、入力が簡単な、シンプルな例で最もよく使用されます。
また、コマンドの構文を示す構文例にも使用されます。

わかりやすい例では、"生の" コード フェンスが使用され、コード ブロックの先頭と末尾をマークします。 コード ブロックには、図示されているコマンドの出力例が含まれている場合があります。

### <a name="syntax-block"></a>構文ブロック

この例は、`Get-Command` コマンドレットのすべての使用できるパラメーターを示しています。

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

この例では、`for` ステートメントを汎用的な用語で説明します。

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="simple-illustration-example"></a>シンプルな図の例

PowerShell の比較演算子の例を次に示します。

~~~markdown
```
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

この例では PowerShell プロンプトが簡略化され、結果の出力が表示されていることに注意してください。 このケースでは、閲覧者がこの例をコピーして実行することは想定していません。

## <a name="formatting-executable-examples"></a>実行可能ファイルの書式設定の例

より複雑な例またはコピーと実行に役立つことを目的とした例では、次のブロックスタイルのマークアップを使用する必要があります。

~~~markdown
```powershell
<PowerShell code goes here>
```
~~~

PowerShell コマンドで表示される出力は、構文の強調表示を防ぐために**出力**コード ブロックで囲む必要があります。 次に例を示します。

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

**Output** コード ラベルは、構文の強調表示システムでサポートされている公式の "言語" ではありません。
ただし、OPS によって Web ページのコード ボックスに "Output" ラベルが追加されるため、このラベルは便利です。
また、この "Output" コード ボックスには構文の強調表示がありません。

## <a name="coding-style-rules"></a>コーディング スタイルの規則

### <a name="avoid-line-continuation-in-code-samples"></a>コード サンプルでの行の継続を避ける

PowerShell コード例では、行連結文字 (`` ` ``) を使用しないでください。 これらはわかりにくいため、行末に余分なスペースがあると問題が発生する可能性があります。

- PowerShell スプラッティングを使用して、多数のパラメーターを持つコマンドレットの行の長さを減らします。
- パイプ (`|`) 文字、左中かっこ、かっこ、角かっこなど、PowerShell の自然な改行の機会を利用します。

### <a name="avoid-using-powershell-prompts-in-examples"></a>例で PowerShell プロンプトを使用しないようにする

プロンプト文字列の使用は推奨されません。また、コマンド ラインの使用方法を示す目的のシナリオに限定する必要があります。 プロンプトを変更するコマンドを示す例、または表示されているパスが説明されているシナリオにとって重要な場合には、プロンプトが必要です。

- PowerShell プロンプトは、わかりやすい例にのみ使用してください。 このような例のほとんどでは、プロンプト文字列は "`PS>`" にする必要があります。 このプロンプトは OS 固有のインジケーターに依存しません。
- プロンプトは、実行可能ファイルの例では**使用しない**でください。

次の例は、レジストリ プロバイダーの使用時にプロンプトがどのように変化するかを示しています。

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a>例でエイリアスを使用しない

エイリアスについて具体的に説明する場合を除き、すべてのコマンドレットとパラメーターの完全な名前を常に使用する必要があります。 コマンドレットとパラメーターの名前には、コードで定義されている適切なパスカル ケースのスペルを使用する必要があります。

### <a name="using-parameters-in-examples"></a>例でのパラメーターの使用

位置指定パラメーターは使用しないでください。 一般的に、パラメーターが位置指定であっても、常に例にパラメーター名を含めるようにします。 これにより、例で混乱を招く可能性が減ります。
