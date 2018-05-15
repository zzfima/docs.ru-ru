---
title: -ресурсов (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab5593455546e65bdd760d9e60532031dc1f12a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="33229-102">-ресурсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33229-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="33229-103">Внедряет управляемый ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="33229-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33229-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33229-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="33229-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="33229-105">Arguments</span></span>  
  
|<span data-ttu-id="33229-106">Термин</span><span class="sxs-lookup"><span data-stu-id="33229-106">Term</span></span>|<span data-ttu-id="33229-107">Определение</span><span class="sxs-lookup"><span data-stu-id="33229-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="33229-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="33229-108">Required.</span></span> <span data-ttu-id="33229-109">Имя файла ресурсов для внедрения в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="33229-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="33229-110">По умолчанию `filename` является открытым в сборке.</span><span class="sxs-lookup"><span data-stu-id="33229-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="33229-111">Заключите имя файла в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="33229-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="33229-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="33229-112">Optional.</span></span> <span data-ttu-id="33229-113">Логическое имя ресурса; имя, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="33229-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="33229-114">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="33229-114">The default is the name of the file.</span></span> <span data-ttu-id="33229-115">Кроме того можно указать, ли ресурс является открытым или закрытым в манифесте сборки, с помощью следующих: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="33229-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33229-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="33229-116">Remarks</span></span>  
 <span data-ttu-id="33229-117">Используйте `-linkresource` чтобы связать ресурс в сборку, не помещая файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="33229-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="33229-118">Если `filename` — [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, он может осуществляться с помощью членов <xref:System.Resources> пространства имен (см. в разделе <xref:System.Resources.ResourceManager> для получения дополнительной информации).</span><span class="sxs-lookup"><span data-stu-id="33229-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="33229-119">Для доступа к другим ресурсам во время выполнения, используйте один из следующих методов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="33229-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="33229-120">Краткой формой `-resource` является `-res`.</span><span class="sxs-lookup"><span data-stu-id="33229-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="33229-121">Сведения о настройке `-resource` в СРЕДЕ Visual Studio в разделе [управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="33229-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33229-122">Пример</span><span class="sxs-lookup"><span data-stu-id="33229-122">Example</span></span>  
 <span data-ttu-id="33229-123">Следующий код компилирует `In.vb` и присоединение файла ресурсов `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="33229-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="33229-124">См. также</span><span class="sxs-lookup"><span data-stu-id="33229-124">See Also</span></span>  
 [<span data-ttu-id="33229-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="33229-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="33229-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="33229-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [<span data-ttu-id="33229-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33229-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [<span data-ttu-id="33229-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33229-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="33229-129">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="33229-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
