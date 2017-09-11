---
title: "Примеры командных строк компиляции (Visual Basic) | Документы Microsoft"
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e58006c05f498ec1a9dbf5194fbc9bcdd281ab63
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="15cd0-102">Примеры командных строк компиляции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15cd0-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="15cd0-103">В качестве альтернативы для компиляции [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы изнутри [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], можно компилировать из командной строки для создания исполняемых файлов (.exe) или файлов библиотеки динамической компоновки (.dll).</span><span class="sxs-lookup"><span data-stu-id="15cd0-103">As an alternative to compiling [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="15cd0-104">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятора командной строки поддерживает полный набор параметров, определяющих входных и выходных файлов, сборки и отладки и параметров препроцессора.</span><span class="sxs-lookup"><span data-stu-id="15cd0-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="15cd0-105">Каждый параметр доступен в двух формах: `-``option` и `/``option`.</span><span class="sxs-lookup"><span data-stu-id="15cd0-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="15cd0-106">В данном документе показана только `/``option` формы.</span><span class="sxs-lookup"><span data-stu-id="15cd0-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="15cd0-107">В следующей таблице перечислены некоторые примеры командных строк, которые можно изменять для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="15cd0-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="15cd0-108">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="15cd0-108">To</span></span>|<span data-ttu-id="15cd0-109">Применение</span><span class="sxs-lookup"><span data-stu-id="15cd0-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="15cd0-110">Компиляция File.vb и создать File.exe</span><span class="sxs-lookup"><span data-stu-id="15cd0-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="15cd0-111">Компиляция File.vb и создание файла File.dll</span><span class="sxs-lookup"><span data-stu-id="15cd0-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="15cd0-112">Компиляция File.vb и создать My.exe</span><span class="sxs-lookup"><span data-stu-id="15cd0-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="15cd0-113">Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге с оптимизацией на и `DEBUG` символ определен, создавая File2.exe</span><span class="sxs-lookup"><span data-stu-id="15cd0-113">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="15cd0-114">Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений</span><span class="sxs-lookup"><span data-stu-id="15cd0-114">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="15cd0-115">Скомпилируйте все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге в Something.dll</span><span class="sxs-lookup"><span data-stu-id="15cd0-115">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="15cd0-116">При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеки времени выполнения с помощью `/reference` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="15cd0-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="15cd0-117">При построении проекта с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** с его параметры компилятора в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="15cd0-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="15cd0-118">Для отображения этих сведений откройте [диалоговое окно «Параметры», проектов и решений, построения и выполнения](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **уровень детализации выходных данных построения проекта MSBuild** для **норм** или более высокий уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="15cd0-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="15cd0-119">Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="15cd0-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cd0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="15cd0-120">See Also</span></span>  
 <span data-ttu-id="15cd0-121">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="15cd0-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="15cd0-122"> [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="15cd0-122"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
