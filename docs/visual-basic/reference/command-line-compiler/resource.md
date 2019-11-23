---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: a781d543dd32ffb3d0ac0b11c544dbfd8cd5d806
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348557"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="7a1b3-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a1b3-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="7a1b3-103">Внедряет управляемый ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a1b3-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="7a1b3-105">or</span><span class="sxs-lookup"><span data-stu-id="7a1b3-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a1b3-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7a1b3-106">Arguments</span></span>  
  
|<span data-ttu-id="7a1b3-107">Термин</span><span class="sxs-lookup"><span data-stu-id="7a1b3-107">Term</span></span>|<span data-ttu-id="7a1b3-108">Определение</span><span class="sxs-lookup"><span data-stu-id="7a1b3-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="7a1b3-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-109">Required.</span></span> <span data-ttu-id="7a1b3-110">The name of the resource file to embed in the output file.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="7a1b3-111">By default, `filename` is public in the assembly.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="7a1b3-112">Enclose the file name in quotation marks (" ") if it contains a space.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="7a1b3-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-113">Optional.</span></span> <span data-ttu-id="7a1b3-114">The logical name for the resource; the name used to load it.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="7a1b3-115">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-115">The default is the name of the file.</span></span> <span data-ttu-id="7a1b3-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="7a1b3-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a1b3-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="7a1b3-117">Remarks</span></span>  
 <span data-ttu-id="7a1b3-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="7a1b3-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span><span class="sxs-lookup"><span data-stu-id="7a1b3-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="7a1b3-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="7a1b3-121">Краткой формой `-resource` является `-res`.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="7a1b3-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7a1b3-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a1b3-123">Пример</span><span class="sxs-lookup"><span data-stu-id="7a1b3-123">Example</span></span>  
 <span data-ttu-id="7a1b3-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="7a1b3-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a1b3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7a1b3-125">See also</span></span>

- [<span data-ttu-id="7a1b3-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7a1b3-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7a1b3-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="7a1b3-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="7a1b3-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a1b3-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="7a1b3-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a1b3-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7a1b3-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7a1b3-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
