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
# <a name="-resource-visual-basic"></a><span data-ttu-id="d764a-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d764a-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="d764a-103">Внедряет управляемый ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="d764a-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d764a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d764a-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="d764a-105">или</span><span class="sxs-lookup"><span data-stu-id="d764a-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d764a-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d764a-106">Arguments</span></span>  
  
|<span data-ttu-id="d764a-107">Термин</span><span class="sxs-lookup"><span data-stu-id="d764a-107">Term</span></span>|<span data-ttu-id="d764a-108">Определение</span><span class="sxs-lookup"><span data-stu-id="d764a-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="d764a-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="d764a-109">Required.</span></span> <span data-ttu-id="d764a-110">Имя файла ресурсов, который необходимо внедрить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="d764a-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="d764a-111">По умолчанию `filename` является общедоступной в сборке.</span><span class="sxs-lookup"><span data-stu-id="d764a-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="d764a-112">Заключите имя файла в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="d764a-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="d764a-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d764a-113">Optional.</span></span> <span data-ttu-id="d764a-114">Логическое имя для ресурса; имя, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="d764a-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="d764a-115">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="d764a-115">The default is the name of the file.</span></span> <span data-ttu-id="d764a-116">При необходимости можно указать, является ли ресурс открытым или закрытым в манифесте сборки, как показано ниже: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="d764a-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d764a-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="d764a-117">Remarks</span></span>  
 <span data-ttu-id="d764a-118">Используйте `-linkresource`, чтобы связать ресурс со сборкой без помещения файла ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="d764a-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="d764a-119">Если `filename` является файлом ресурсов .NET Framework, который создается, например, программой [Resgen. exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, доступ к нему можно получить с помощью членов пространства имен <xref:System.Resources> (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>).</span><span class="sxs-lookup"><span data-stu-id="d764a-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="d764a-120">Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте один из следующих методов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="d764a-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="d764a-121">Краткой формой `-resource` является `-res`.</span><span class="sxs-lookup"><span data-stu-id="d764a-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="d764a-122">Сведения о том, как задать `-resource` в интегрированной среде разработки Visual Studio, см. в разделе [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d764a-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d764a-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d764a-123">Example</span></span>  
 <span data-ttu-id="d764a-124">Следующий код компилирует `In.vb` и присоединяет `Rf.resource`файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d764a-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d764a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d764a-125">See also</span></span>

- [<span data-ttu-id="d764a-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d764a-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d764a-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="d764a-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="d764a-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d764a-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="d764a-129">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d764a-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="d764a-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d764a-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
