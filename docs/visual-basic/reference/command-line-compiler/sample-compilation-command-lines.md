---
title: Примеры командных строк компиляции (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046283"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="dffc4-102">Примеры командных строк компиляции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dffc4-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="dffc4-103">В качестве альтернативы компиляции Visual Basic программ из Visual Studio можно выполнить компиляцию из командной строки, чтобы создать исполняемые файлы (exe) или файлы библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="dffc4-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="dffc4-104">Компилятор командной строки Visual Basic поддерживает полный набор параметров, управляющих входными и выходными файлами, сборками, параметрами отладки и препроцессором.</span><span class="sxs-lookup"><span data-stu-id="dffc4-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="dffc4-105">Каждый параметр доступен в двух взаимозаменяемых формах: `-option` и. `/option`</span><span class="sxs-lookup"><span data-stu-id="dffc4-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="dffc4-106">В `-option` этой документации показана только форма.</span><span class="sxs-lookup"><span data-stu-id="dffc4-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="dffc4-107">В следующей таблице перечислены некоторые примеры командных строк, которые можно изменить для собственного использования.</span><span class="sxs-lookup"><span data-stu-id="dffc4-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="dffc4-108">Кому</span><span class="sxs-lookup"><span data-stu-id="dffc4-108">To</span></span>|<span data-ttu-id="dffc4-109">Использовать</span><span class="sxs-lookup"><span data-stu-id="dffc4-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="dffc4-110">Скомпилируйте файл File. vb и создайте файл. exe</span><span class="sxs-lookup"><span data-stu-id="dffc4-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="dffc4-111">Скомпилируйте файл File. vb и создайте файл. dll</span><span class="sxs-lookup"><span data-stu-id="dffc4-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="dffc4-112">Скомпилируйте файл File. vb и создайте My. exe</span><span class="sxs-lookup"><span data-stu-id="dffc4-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="dffc4-113">Скомпилируйте файл File. vb и создайте библиотеку и ссылочную сборку с именем file. dll</span><span class="sxs-lookup"><span data-stu-id="dffc4-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="dffc4-114">Компилировать все файлы Visual Basic в текущем каталоге с оптимизацией и `DEBUG` определенным символом, создавая file2. exe.</span><span class="sxs-lookup"><span data-stu-id="dffc4-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="dffc4-115">Компилировать все файлы Visual Basic в текущем каталоге, создавая отладочную версию file2. DLL без отображения логотипа или предупреждений</span><span class="sxs-lookup"><span data-stu-id="dffc4-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="dffc4-116">Компилировать все файлы Visual Basic в текущем каталоге в файл. dll</span><span class="sxs-lookup"><span data-stu-id="dffc4-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="dffc4-117">При построении проекта с помощью интегрированной среды разработки Visual Studio можно отобразить сведения о связанной команде **vbc** с ее параметрами компилятора в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="dffc4-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="dffc4-118">Чтобы отобразить эти сведения, откройте [диалоговое окно Параметры, проекты и решения, сборка и запуск](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), а затем задайте для параметра **уровень детализации выходных данных сборки проекта MSBuild** значение **обычное** или более высокий уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="dffc4-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="dffc4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dffc4-119">See also</span></span>

- [<span data-ttu-id="dffc4-120">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="dffc4-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="dffc4-121">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="dffc4-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
