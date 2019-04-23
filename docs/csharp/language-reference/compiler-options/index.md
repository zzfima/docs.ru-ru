---
title: Параметры компилятора C#
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: a0affaf3691d2392c9f8d7502204d0122f2ea428
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61662833"
---
# <a name="c-compiler-options"></a><span data-ttu-id="df7bd-102">Параметры компилятора C#</span><span class="sxs-lookup"><span data-stu-id="df7bd-102">C# Compiler Options</span></span>
<span data-ttu-id="df7bd-103">Компилятор создает исполняемые файлы (EXE-файлы), библиотеки динамической компоновки (DLL-файлы) или модули кода (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="df7bd-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="df7bd-104">Каждый параметр компилятора можно использовать в двух формах записи: **-параметр** или **/параметр**.</span><span class="sxs-lookup"><span data-stu-id="df7bd-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="df7bd-105">В документации показана только форма **-<параметр>**.</span><span class="sxs-lookup"><span data-stu-id="df7bd-105">The documentation only shows the **-option** form.</span></span>  
  
 <span data-ttu-id="df7bd-106">В Visual Studio параметры компилятора задаются в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="df7bd-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="df7bd-107">Дополнительные сведения см. в разделе [\<компилятор> Элемент](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="df7bd-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df7bd-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="df7bd-108">In This Section</span></span>  
 [<span data-ttu-id="df7bd-109">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="df7bd-109">Command-line Building With csc.exe</span></span>](command-line-building-with-csc-exe.md)  
 <span data-ttu-id="df7bd-110">Сведения о сборке приложения Visual C# из командной строки.</span><span class="sxs-lookup"><span data-stu-id="df7bd-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="df7bd-111">Практическое руководство. Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df7bd-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="df7bd-112">Предоставляет пошаговые инструкции по выполнению vsvars32.bat для сборки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="df7bd-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="df7bd-113">Параметры компилятора C#, упорядоченные по категориям</span><span class="sxs-lookup"><span data-stu-id="df7bd-113">C# Compiler Options Listed by Category</span></span>](listed-by-category.md)  
 <span data-ttu-id="df7bd-114">Категоризированный список параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="df7bd-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="df7bd-115">Параметры компилятора C# в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="df7bd-115">C# Compiler Options Listed Alphabetically</span></span>](listed-alphabetically.md)  
 <span data-ttu-id="df7bd-116">Отсортированный по алфавиту список параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="df7bd-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="df7bd-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="df7bd-117">Related Sections</span></span>  
 <span data-ttu-id="df7bd-118">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) (Страница "Сборка" в конструкторе проектов)</span><span class="sxs-lookup"><span data-stu-id="df7bd-118">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp)</span></span>  
 <span data-ttu-id="df7bd-119">Описывает свойства, влияющие на процессы компиляции, сборки и отладки проекта.</span><span class="sxs-lookup"><span data-stu-id="df7bd-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="df7bd-120">Содержит сведения о настраиваемых этапах сборки для проектов Visual C#.</span><span class="sxs-lookup"><span data-stu-id="df7bd-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 <span data-ttu-id="df7bd-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) (Сборки по умолчанию и пользовательские сборки)</span><span class="sxs-lookup"><span data-stu-id="df7bd-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio)</span></span>  
 <span data-ttu-id="df7bd-122">Сведения о типах сборки и конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="df7bd-122">Information on build types and configurations.</span></span>  
  
 <span data-ttu-id="df7bd-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Подготовка к сборке и управление сборкой)</span><span class="sxs-lookup"><span data-stu-id="df7bd-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)</span></span>  
 <span data-ttu-id="df7bd-124">Процедуры выполнения сборки в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="df7bd-124">Procedures for building within the Visual Studio development environment.</span></span>
