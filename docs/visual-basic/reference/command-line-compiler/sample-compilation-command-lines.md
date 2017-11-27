---
title: "Примеры командных строк компиляции (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="3f787-102">Примеры командных строк компиляции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f787-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="3f787-103">В качестве альтернативы для компиляции [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы изнутри [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], можно скомпилировать из командной строки для создания исполняемых файлов (.exe) или файлы библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="3f787-103">As an alternative to compiling [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="3f787-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор командной строки поддерживает полный набор параметров, входные и выходные файлы, сборки и отладки элементов управления и параметров препроцессора.</span><span class="sxs-lookup"><span data-stu-id="3f787-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="3f787-105">Каждый параметр доступен в двух формах: `-``option` и `/``option`.</span><span class="sxs-lookup"><span data-stu-id="3f787-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="3f787-106">В данном документе показана только `/``option` формы.</span><span class="sxs-lookup"><span data-stu-id="3f787-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="3f787-107">В следующей таблице перечислены некоторые примеры команд командной строки, которые можно изменять для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="3f787-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="3f787-108">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="3f787-108">To</span></span>|<span data-ttu-id="3f787-109">Применение</span><span class="sxs-lookup"><span data-stu-id="3f787-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="3f787-110">Скомпилируйте файл VB и создайте File.exe</span><span class="sxs-lookup"><span data-stu-id="3f787-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="3f787-111">Скомпилируйте файл VB и создайте File.dll</span><span class="sxs-lookup"><span data-stu-id="3f787-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="3f787-112">Скомпилируйте файл VB и создайте My.exe</span><span class="sxs-lookup"><span data-stu-id="3f787-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="3f787-113">Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге с оптимизацией и `DEBUG` символ определен, формирующего File2.exe</span><span class="sxs-lookup"><span data-stu-id="3f787-113">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="3f787-114">Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений</span><span class="sxs-lookup"><span data-stu-id="3f787-114">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="3f787-115">Скомпилируйте все [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлы в текущем каталоге в Something.dll</span><span class="sxs-lookup"><span data-stu-id="3f787-115">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="3f787-116">При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] библиотеку времени выполнения с помощью `/reference` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="3f787-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="3f787-117">При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="3f787-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="3f787-118">Чтобы отобразить эти сведения, откройте [диалоговое окно «Параметры», проекты и решения, построения и выполнения](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **детализации, выходные данные построения проекта MSBuild** для **обычный** или более высоком уровне детализации.</span><span class="sxs-lookup"><span data-stu-id="3f787-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="3f787-119">Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="3f787-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f787-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3f787-120">See Also</span></span>  
 [<span data-ttu-id="3f787-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="3f787-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3f787-122">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="3f787-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
