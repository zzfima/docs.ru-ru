---
title: Примеры командных строк компиляции (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b61ef6facf33fa043cad28a78405a19308a9864f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="964f1-102">Примеры командных строк компиляции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="964f1-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="964f1-103">В качестве альтернативы для компиляции Visual Basic в Visual Studio можно компилировать из командной строки для создания исполняемых файлов (.exe) или файлы библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="964f1-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="964f1-104">Компилятор командной строки Visual Basic поддерживает полный набор параметров для управления входными и выходные файлы, сборки, отладки и параметры препроцессора.</span><span class="sxs-lookup"><span data-stu-id="964f1-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="964f1-105">Каждый параметр доступен в двух формах: `-option` и `/option`.</span><span class="sxs-lookup"><span data-stu-id="964f1-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="964f1-106">В данном документе показана только `-option` формы.</span><span class="sxs-lookup"><span data-stu-id="964f1-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="964f1-107">В следующей таблице перечислены некоторые примеры команд командной строки, которые можно изменять для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="964f1-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="964f1-108">Кому</span><span class="sxs-lookup"><span data-stu-id="964f1-108">To</span></span>|<span data-ttu-id="964f1-109">Использовать</span><span class="sxs-lookup"><span data-stu-id="964f1-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="964f1-110">Скомпилируйте файл VB и создайте File.exe</span><span class="sxs-lookup"><span data-stu-id="964f1-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="964f1-111">Скомпилируйте файл VB и создайте File.dll</span><span class="sxs-lookup"><span data-stu-id="964f1-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="964f1-112">Скомпилируйте файл VB и создайте My.exe</span><span class="sxs-lookup"><span data-stu-id="964f1-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="964f1-113">Скомпилируйте файл VB и создание библиотеки и ссылочную сборку с именем File.dll</span><span class="sxs-lookup"><span data-stu-id="964f1-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="964f1-114">Компилировать все файлы Visual Basic в текущем каталоге с оптимизацией на и `DEBUG` символ определен, формирующего File2.exe</span><span class="sxs-lookup"><span data-stu-id="964f1-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="964f1-115">Компилировать все файлы Visual Basic в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений</span><span class="sxs-lookup"><span data-stu-id="964f1-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="964f1-116">Компилировать все файлы Visual Basic в текущем каталоге в Something.dll</span><span class="sxs-lookup"><span data-stu-id="964f1-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="964f1-117">При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="964f1-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="964f1-118">Чтобы отобразить эти сведения, откройте [диалоговое окно «Параметры», проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **детализации, выходные данные построения проекта MSBuild** для **обычный** или более высоком уровне детализации.</span><span class="sxs-lookup"><span data-stu-id="964f1-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="964f1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="964f1-119">See Also</span></span>  
 [<span data-ttu-id="964f1-120">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="964f1-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="964f1-121">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="964f1-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
