---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 97e0ccd46f413cc05b659731436bb141ee178419
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44369034"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="5c360-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c360-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="5c360-103">Создает ссылку на управляемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="5c360-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c360-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c360-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c360-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5c360-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="5c360-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="5c360-106">Required.</span></span> <span data-ttu-id="5c360-107">Файл ресурсов, ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="5c360-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="5c360-108">Если имя файла содержит пробел, заключите имя в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="5c360-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="5c360-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5c360-109">Optional.</span></span> <span data-ttu-id="5c360-110">Логическое имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c360-110">The logical name for the resource.</span></span> <span data-ttu-id="5c360-111">Имя, которое используется для загрузки ресурса.</span><span class="sxs-lookup"><span data-stu-id="5c360-111">The name that is used to load the resource.</span></span> <span data-ttu-id="5c360-112">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="5c360-112">The default is the name of the file.</span></span> <span data-ttu-id="5c360-113">При необходимости можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="5c360-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="5c360-114">По умолчанию `filename` является открытым в сборке.</span><span class="sxs-lookup"><span data-stu-id="5c360-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c360-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c360-115">Remarks</span></span>  
 <span data-ttu-id="5c360-116">`-linkresource` Параметр не внедрить файл ресурсов в выходной файл; используйте `-resource` параметр, чтобы это сделать.</span><span class="sxs-lookup"><span data-stu-id="5c360-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="5c360-117">`-linkresource` Параметр требует одного из `-target` параметры, отличные от `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="5c360-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="5c360-118">Если `filename` — [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файл ресурсов, созданным, например, по [Resgen.exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, он может осуществляться с помощью членов пространства <xref:System.Resources> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5c360-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="5c360-119">(Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Чтобы получить доступ к всем остальным ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в <xref:System.Reflection.Assembly> класса.</span><span class="sxs-lookup"><span data-stu-id="5c360-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="5c360-120">Имя файла может иметь любой формат файла.</span><span class="sxs-lookup"><span data-stu-id="5c360-120">The file name can be any file format.</span></span> <span data-ttu-id="5c360-121">Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.</span><span class="sxs-lookup"><span data-stu-id="5c360-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="5c360-122">Краткой формой `-linkresource` является `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="5c360-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c360-123">`-linkresource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5c360-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c360-124">Пример</span><span class="sxs-lookup"><span data-stu-id="5c360-124">Example</span></span>  
 <span data-ttu-id="5c360-125">Следующий код компилирует `in.vb` и ссылки на файл ресурсов `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="5c360-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c360-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5c360-126">See also</span></span>

- [<span data-ttu-id="5c360-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="5c360-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
- [<span data-ttu-id="5c360-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c360-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
- [<span data-ttu-id="5c360-129">-ресурсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c360-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
- [<span data-ttu-id="5c360-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="5c360-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
