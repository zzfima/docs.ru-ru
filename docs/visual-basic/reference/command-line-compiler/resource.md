---
title: "/ Resource (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2278902f96f7b6349e91a9803f58c3caa89f4f33
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="resource-visual-basic"></a><span data-ttu-id="46531-102">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46531-102">/resource (Visual Basic)</span></span>
<span data-ttu-id="46531-103">Внедряет управляемый ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="46531-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46531-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46531-104">Syntax</span></span>  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="46531-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="46531-105">Arguments</span></span>  
  
|<span data-ttu-id="46531-106">Термин</span><span class="sxs-lookup"><span data-stu-id="46531-106">Term</span></span>|<span data-ttu-id="46531-107">Определение</span><span class="sxs-lookup"><span data-stu-id="46531-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="46531-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="46531-108">Required.</span></span> <span data-ttu-id="46531-109">Имя файла ресурсов для внедрения в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="46531-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="46531-110">По умолчанию `filename` является открытым в сборке.</span><span class="sxs-lookup"><span data-stu-id="46531-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="46531-111">Заключите имя файла в кавычки («»), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="46531-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="46531-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="46531-112">Optional.</span></span> <span data-ttu-id="46531-113">Логическое имя ресурса; имя, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="46531-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="46531-114">Значение по умолчанию — имя файла.</span><span class="sxs-lookup"><span data-stu-id="46531-114">The default is the name of the file.</span></span> <span data-ttu-id="46531-115">При необходимости можно указать ли ресурс открытым или закрытым в манифесте сборки с помощью следующих: `/res:``filename.res`,`myname.res`,`public`</span><span class="sxs-lookup"><span data-stu-id="46531-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `/res:``filename.res`,`myname.res`,`public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46531-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="46531-116">Remarks</span></span>  
 <span data-ttu-id="46531-117">Используйте `/linkresource` , чтобы связать ресурс и сборку, не помещая файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="46531-117">Use `/linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="46531-118">Если `filename` — [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, может осуществляться с помощью членов <xref:System.Resources>пространства имен (см. <xref:System.Resources.ResourceManager>Дополнительные сведения).</xref:System.Resources.ResourceManager> </xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="46531-118">If `filename` is a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="46531-119">Для доступа к другим ресурсам во время выполнения, используйте один из следующих способов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A></span><span class="sxs-lookup"><span data-stu-id="46531-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="46531-120">Краткая форма `/resource` — `/res`.</span><span class="sxs-lookup"><span data-stu-id="46531-120">The short form of `/resource` is `/res`.</span></span>  
  
 <span data-ttu-id="46531-121">Дополнительные сведения о настройке `/resource` в СРЕДЕ Visual Studio в разделе [управление ресурсами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="46531-121">For information about how to set `/resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46531-122">Пример</span><span class="sxs-lookup"><span data-stu-id="46531-122">Example</span></span>  
 <span data-ttu-id="46531-123">Следующий код компилирует `In.vb` и присоединение файла ресурсов `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="46531-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="46531-124">См. также</span><span class="sxs-lookup"><span data-stu-id="46531-124">See Also</span></span>  
 <span data-ttu-id="46531-125">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="46531-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="46531-126"> [/ win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span><span class="sxs-lookup"><span data-stu-id="46531-126"> [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) </span></span>  
<span data-ttu-id="46531-127"> [/ linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span><span class="sxs-lookup"><span data-stu-id="46531-127"> [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) </span></span>  
<span data-ttu-id="46531-128"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="46531-128"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="46531-129"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="46531-129"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
