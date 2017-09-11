---
title: "Параметры компилятора C#"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.options
dev_langs:
- CSharp
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 02cfb7708959057de593506db55e4f31f5ab4fd0
ms.openlocfilehash: 7c5f5274a5685e50fb7f1d06771b0340200d1c3f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/28/2017

---
# <a name="c-compiler-options"></a><span data-ttu-id="cc2a4-102">Параметры компилятора C#</span><span class="sxs-lookup"><span data-stu-id="cc2a4-102">C# Compiler Options</span></span>
<span data-ttu-id="cc2a4-103">Компилятор создает исполняемые файлы (EXE-файлы), библиотеки динамической компоновки (DLL-файлы) или модули кода (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="cc2a4-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="cc2a4-104">Каждый параметр компилятора можно использовать в двух формах записи: **-параметр** или **/параметр**.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="cc2a4-105">В документации используется только вариант **/параметр**.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-105">The documentation only shows the **/option** form.</span></span>  
  
 <span data-ttu-id="cc2a4-106">В Visual Web Developer 2008 параметры компилятора задаются в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-106">In Visual Web Developer 2008, you set compiler options in the web.config file.</span></span> <span data-ttu-id="cc2a4-107">Дополнительные сведения см. в разделе [\<компилятор> Элемент](https://msdn.microsoft.com/library/y9x69bzw).</span><span class="sxs-lookup"><span data-stu-id="cc2a4-107">For more information, see [\<compiler> Element](https://msdn.microsoft.com/library/y9x69bzw).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc2a4-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="cc2a4-108">In This Section</span></span>  
 [<span data-ttu-id="cc2a4-109">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="cc2a4-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 <span data-ttu-id="cc2a4-110">Сведения о сборке приложения Visual C# из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="cc2a4-111">Практическое руководство. Настройка переменных среды для командной строки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc2a4-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="cc2a4-112">Предоставляет пошаговые инструкции по выполнению vsvars32.bat для сборки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="cc2a4-113">Параметры компилятора C#, упорядоченные по категориям</span><span class="sxs-lookup"><span data-stu-id="cc2a4-113">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 <span data-ttu-id="cc2a4-114">Категоризированный список параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="cc2a4-115">Параметры компилятора C# в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="cc2a4-115">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 <span data-ttu-id="cc2a4-116">Отсортированный по алфавиту список параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cc2a4-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cc2a4-117">Related Sections</span></span>  
 <span data-ttu-id="cc2a4-118">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) (Страница "Сборка" в конструкторе проектов)</span><span class="sxs-lookup"><span data-stu-id="cc2a4-118">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp)</span></span>  
 <span data-ttu-id="cc2a4-119">Описывает свойства, влияющие на процессы компиляции, сборки и отладки проекта.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="cc2a4-120">Содержит сведения о настраиваемых этапах сборки для проектов Visual C#.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 <span data-ttu-id="cc2a4-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) (Сборки по умолчанию и пользовательские сборки)</span><span class="sxs-lookup"><span data-stu-id="cc2a4-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio)</span></span>  
 <span data-ttu-id="cc2a4-122">Сведения о типах сборки и конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-122">Information on build types and configurations.</span></span>  
  
 <span data-ttu-id="cc2a4-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Подготовка к сборке и управление сборкой)</span><span class="sxs-lookup"><span data-stu-id="cc2a4-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)</span></span>  
 <span data-ttu-id="cc2a4-124">Процедуры выполнения сборки в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cc2a4-124">Procedures for building within the Visual Studio development environment.</span></span>

