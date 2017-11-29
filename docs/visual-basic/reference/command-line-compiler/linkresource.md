---
title: /linkresource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="d3f28-102">/linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3f28-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="d3f28-103">Создает ссылку на управляемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="d3f28-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3f28-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3f28-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d3f28-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="d3f28-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d3f28-106">Required.</span></span> <span data-ttu-id="d3f28-107">Файл ресурсов, ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="d3f28-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="d3f28-108">Если имя файла содержит пробелы, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="d3f28-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="d3f28-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d3f28-109">Optional.</span></span> <span data-ttu-id="d3f28-110">Логическое имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="d3f28-110">The logical name for the resource.</span></span> <span data-ttu-id="d3f28-111">Имя, которое используется для загрузки ресурса.</span><span class="sxs-lookup"><span data-stu-id="d3f28-111">The name that is used to load the resource.</span></span> <span data-ttu-id="d3f28-112">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="d3f28-112">The default is the name of the file.</span></span> <span data-ttu-id="d3f28-113">Кроме того, можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `/linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="d3f28-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="d3f28-114">По умолчанию `filename` является открытым в сборке.</span><span class="sxs-lookup"><span data-stu-id="d3f28-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3f28-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3f28-115">Remarks</span></span>  
 <span data-ttu-id="d3f28-116">`/linkresource` Параметр нельзя внедрить файл ресурсов в выходной файл; используйте `/resource` параметр, чтобы сделать это.</span><span class="sxs-lookup"><span data-stu-id="d3f28-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="d3f28-117">`/linkresource` Параметра необходим один из `/target` параметры отличный от `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="d3f28-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="d3f28-118">Если `filename` — [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, он может осуществляться с помощью членов <xref:System.Resources> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d3f28-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="d3f28-119">(Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Для доступа к другим ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в <xref:System.Reflection.Assembly> класса.</span><span class="sxs-lookup"><span data-stu-id="d3f28-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="d3f28-120">Имя файла может иметь любой формат файла.</span><span class="sxs-lookup"><span data-stu-id="d3f28-120">The file name can be any file format.</span></span> <span data-ttu-id="d3f28-121">Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.</span><span class="sxs-lookup"><span data-stu-id="d3f28-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="d3f28-122">Краткой формой `/linkresource` является `/linkres`.</span><span class="sxs-lookup"><span data-stu-id="d3f28-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3f28-123">`/linkresource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d3f28-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3f28-124">Пример</span><span class="sxs-lookup"><span data-stu-id="d3f28-124">Example</span></span>  
 <span data-ttu-id="d3f28-125">Следующий код компилирует `In.vb` и ссылки на файл ресурсов `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="d3f28-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3f28-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d3f28-126">See Also</span></span>  
 [<span data-ttu-id="d3f28-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d3f28-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d3f28-128">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3f28-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="d3f28-129">/ Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3f28-129">/resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="d3f28-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d3f28-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
