---
title: "Построение из командной строки (Visual Basic) | Документы Microsoft"
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
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers, invoking from command line
- command-line builds
- compiling source code
- command-line compilers, Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
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
ms.openlocfilehash: e7550a4a54637ea5ef425a1cb7ae02abd07808a8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="ee7ad-102">Построение из командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee7ad-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="ee7ad-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проект состоит из одного или нескольких файлов отдельный источник.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="ee7ad-104">В процессе компиляции эти файлы соединяются в один пакет — исполняемый файл, который запускается как приложение.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ee7ad-105">предоставляет компилятор командной строки в качестве альтернативы для компиляции программы с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] интегрированной среды разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="ee7ad-106">Компилятор командной строки разработан для ситуаций, в которых не требуется полный набор функций в Интегрированной среде разработки, например, при использовании или создании программы на компьютере с ограниченными системными ресурсами или дисковым пространством.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="ee7ad-107">При компиляции из командной строки, необходимо явно ссылаться Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеки времени выполнения с помощью `/reference` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="ee7ad-108">Для компиляции исходных файлов из [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] интегрированной среды разработки, выберите **построения** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-108">To compile source files from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ee7ad-109">При построении проекта файлы с помощью Visual Studio IDE можно отобразить сведения о связанном **vbc** команду и ее параметры в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="ee7ad-110">Для отображения этих сведений откройте [диалоговое окно «Параметры», проектов и решений, построения и выполнения](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)и задайте **уровень детализации выходных данных построения проекта MSBuild** для **норм** или более высокий уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="ee7ad-111">Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="ee7ad-112">Файлы проекта (VBPROJ) в командной строке можно скомпилировать с помощью MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="ee7ad-113">Дополнительные сведения см. в разделе [Справочник по командной строки](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство: использование MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).</span><span class="sxs-lookup"><span data-stu-id="ee7ad-113">For more information, see [Command-Line Reference](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee7ad-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="ee7ad-114">In This Section</span></span>  
 [<span data-ttu-id="ee7ad-115">Практическое руководство. Вызов компилятора командной строки</span><span class="sxs-lookup"><span data-stu-id="ee7ad-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="ee7ad-116">Описывается вызов компилятора командной строки, в командной строке MS-DOS или из определенной папки.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="ee7ad-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ee7ad-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="ee7ad-118">Список примеров командных строк, которые можно изменять для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee7ad-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ee7ad-119">Related Sections</span></span>  
 [<span data-ttu-id="ee7ad-120">Компилятор командной строки Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee7ad-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="ee7ad-121">Предоставляет список параметров компилятора, упорядоченные по алфавиту или по назначению.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="ee7ad-122">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="ee7ad-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="ee7ad-123">Способы компиляции определенных частей кода.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-123">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="ee7ad-124">Построение и очистка проектов и решений в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ee7ad-124">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="ee7ad-125">В этой статье описывается организация состава отдельных сборок, изменение свойств проекта и убедитесь, что построение проектов в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ee7ad-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
