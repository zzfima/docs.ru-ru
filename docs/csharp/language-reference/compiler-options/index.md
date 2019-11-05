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
ms.openlocfilehash: dab91ddd1f2b9c91560329eeb1c51ca7f6f175bd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455247"
---
# <a name="c-compiler-options"></a><span data-ttu-id="d4cd5-102">Параметры компилятора C#</span><span class="sxs-lookup"><span data-stu-id="d4cd5-102">C# Compiler Options</span></span>

<span data-ttu-id="d4cd5-103">Компилятор создает исполняемые файлы (EXE-файлы), библиотеки динамической компоновки (DLL-файлы) или модули кода (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="d4cd5-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="d4cd5-104">Каждый параметр компилятора можно использовать в двух формах записи: **-параметр** или **/параметр**.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="d4cd5-105">В документации показана только форма **-<параметр>** .</span><span class="sxs-lookup"><span data-stu-id="d4cd5-105">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="d4cd5-106">В Visual Studio параметры компилятора задаются в файле *web.config*.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-106">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="d4cd5-107">Дополнительные сведения см. в разделе [\<компилятор> Элемент](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="d4cd5-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d4cd5-108">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="d4cd5-108">In this section</span></span>

- <span data-ttu-id="d4cd5-109">[Создание из командной строки с помощью csc.exe](command-line-building-with-csc-exe.md) — сведения о создании приложений Visual C# из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-109">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="d4cd5-110">[Практическое руководство. Настройка переменных среды для командной строки Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md) — пошаговые инструкции по запуску файла *vsvars32.bat* для создания приложений из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-110">[How to: Set Environment Variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="d4cd5-111">[Параметры компилятора C#, перечисленные по категории](listed-by-category.md) — список параметров компилятора по категориям.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-111">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="d4cd5-112">[Параметры компилятора C#, перечисленные по алфавиту](listed-alphabetically.md) — список параметров компилятора по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-112">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d4cd5-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d4cd5-113">Related sections</span></span>

- <span data-ttu-id="d4cd5-114">[Страница сборки, конструктор проектов](/visualstudio/ide/reference/build-page-project-designer-csharp) — настройка свойств, управляющих компиляцией, сборкой и отладкой проекта.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-114">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="d4cd5-115">Содержит сведения о настраиваемых этапах сборки для проектов Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-115">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="d4cd5-116">[Сборки по умолчанию и пользовательские сборки](/visualstudio/ide/compiling-and-building-in-visual-studio) — сведения о конфигурациях и типах сборок.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-116">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="d4cd5-117">[Подготовка и администрирование сборок](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) — создание приложений в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-117">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
