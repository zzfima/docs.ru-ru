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
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924863"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="484b6-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="484b6-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="484b6-103">Создает ссылку на управляемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="484b6-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="484b6-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="484b6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="484b6-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="484b6-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="484b6-106">Required.</span></span> <span data-ttu-id="484b6-107">Файл ресурсов, связываемый с сборкой.</span><span class="sxs-lookup"><span data-stu-id="484b6-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="484b6-108">Если имя файла содержит пробел, заключите его в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="484b6-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="484b6-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="484b6-109">Optional.</span></span> <span data-ttu-id="484b6-110">Логическое имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="484b6-110">The logical name for the resource.</span></span> <span data-ttu-id="484b6-111">Имя, используемое для загрузки ресурса.</span><span class="sxs-lookup"><span data-stu-id="484b6-111">The name that is used to load the resource.</span></span> <span data-ttu-id="484b6-112">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="484b6-112">The default is the name of the file.</span></span> <span data-ttu-id="484b6-113">При необходимости можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="484b6-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="484b6-114">По умолчанию `filename` является общедоступным в сборке.</span><span class="sxs-lookup"><span data-stu-id="484b6-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="484b6-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="484b6-115">Remarks</span></span>  
 <span data-ttu-id="484b6-116">Параметр не внедряет файл ресурсов в выходной файл. для этого `-resource` используйте параметр. `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="484b6-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="484b6-117">Для `-linkresource` параметра требуется один `-target` из параметров `-target:module`, кроме.</span><span class="sxs-lookup"><span data-stu-id="484b6-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="484b6-118">Если `filename` — это .NET Frameworkный файл ресурсов, например [Resgen. exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, доступ к нему можно получить <xref:System.Resources> с помощью членов пространства имен.</span><span class="sxs-lookup"><span data-stu-id="484b6-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="484b6-119">(Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы, `GetManifestResource` начинающиеся <xref:System.Reflection.Assembly> с класса.</span><span class="sxs-lookup"><span data-stu-id="484b6-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="484b6-120">Имя файла может быть любым форматом файла.</span><span class="sxs-lookup"><span data-stu-id="484b6-120">The file name can be any file format.</span></span> <span data-ttu-id="484b6-121">Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.</span><span class="sxs-lookup"><span data-stu-id="484b6-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="484b6-122">Краткой формой `-linkresource` является `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="484b6-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="484b6-123">Этот `-linkresource` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="484b6-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="484b6-124">Пример</span><span class="sxs-lookup"><span data-stu-id="484b6-124">Example</span></span>  
 <span data-ttu-id="484b6-125">Следующий код компилирует `in.vb` и ссылается на файл `rf.resource`ресурсов.</span><span class="sxs-lookup"><span data-stu-id="484b6-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="484b6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="484b6-126">See also</span></span>

- [<span data-ttu-id="484b6-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="484b6-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="484b6-128">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="484b6-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="484b6-129">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="484b6-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="484b6-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="484b6-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
