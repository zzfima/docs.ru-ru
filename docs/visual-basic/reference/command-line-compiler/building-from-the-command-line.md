---
title: Построение из командной строки
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344797"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="4870b-102">Построение из командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4870b-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="4870b-103">Проект Visual Basic состоит из одного или нескольких отдельных исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="4870b-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="4870b-104">В ходе процесса, известного как компиляция, эти файлы объединяются в один пакет — один исполняемый файл, который можно запустить как приложение.</span><span class="sxs-lookup"><span data-stu-id="4870b-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="4870b-105">Visual Basic предоставляет компилятор командной строки в качестве альтернативы компиляции программ из интегрированной среды разработки (IDE) Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4870b-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="4870b-106">Компилятор командной строки предназначен для ситуаций, в которых не требуется полный набор функций в интегрированной среде разработки (например, при использовании или записи для компьютеров с ограниченным объемом системной памяти или дискового пространства).</span><span class="sxs-lookup"><span data-stu-id="4870b-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="4870b-107">Чтобы скомпилировать исходные файлы в интегрированной среде разработки Visual Studio, выберите команду **построить** в меню **Сборка** .</span><span class="sxs-lookup"><span data-stu-id="4870b-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="4870b-108">При создании файлов проекта с помощью интегрированной среды разработки Visual Studio можно отобразить сведения о соответствующей команде **vbc** и ее параметрах в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="4870b-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="4870b-109">Чтобы отобразить эти сведения, откройте [диалоговое окно Параметры, проекты и решения, сборка и запуск](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем задайте для параметра **уровень детализации выходных данных сборки проекта MSBuild** значение **обычное** или более высокий уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="4870b-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="4870b-110">Дополнительные сведения см. в статье [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="4870b-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="4870b-111">Файлы проекта (VBPROJ) можно компилировать в командной строке с помощью MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4870b-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="4870b-112">Дополнительные сведения см. в разделе [Справочник по командной строке](/visualstudio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство. Использование MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="4870b-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4870b-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4870b-113">In This Section</span></span>

<span data-ttu-id="4870b-114">[Как вызвать компилятор командной строки](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="4870b-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="4870b-115">Описание вызова компилятора командной строки в командной строке MS-DOS или в определенном подкаталоге.</span><span class="sxs-lookup"><span data-stu-id="4870b-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="4870b-116">[Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="4870b-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="4870b-117">Содержит список примеров командных строк, которые можно изменить для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="4870b-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="4870b-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4870b-118">Related Sections</span></span>

<span data-ttu-id="4870b-119">[Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="4870b-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="4870b-120">Предоставляет списки параметров компилятора, упорядоченные в алфавитном порядке или по назначению.</span><span class="sxs-lookup"><span data-stu-id="4870b-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="4870b-121"> \ [условной компиляции](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="4870b-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) \</span></span>
<span data-ttu-id="4870b-122">Описывает, как компилировать определенные фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="4870b-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="4870b-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \ (Построение и очистка проектов и решений в Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4870b-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \</span></span>
<span data-ttu-id="4870b-124">Описывается способ организации того, что будет включаться в разные сборки, выберите Свойства проекта и убедитесь, что проекты строятся в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="4870b-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
