---
title: Учебник. Создание средства для анализа и исправления кода
description: В этом руководстве описано, как создать анализатор и исправление кода с помощью пакета SDK для .NET Compiler Platform (API Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: 99401e74588088d56b3fbd916e050f5d468722a1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346938"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="2130e-103">Учебник. Создание средства для анализа и исправления кода</span><span class="sxs-lookup"><span data-stu-id="2130e-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="2130e-104">Пакет SDK для .NET Compiler Platform предоставляет инструменты для создания пользовательских предупреждений для кода C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2130e-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="2130e-105">**Анализатор** содержит код, который распознает нарушения правила.</span><span class="sxs-lookup"><span data-stu-id="2130e-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="2130e-106">**Исправление кода** содержит код, который исправляет эти нарушения.</span><span class="sxs-lookup"><span data-stu-id="2130e-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="2130e-107">Правилами, которые вы реализуете, может быть что угодно — от структуры кода до его стиля или соглашений об именовании и многое другое.</span><span class="sxs-lookup"><span data-stu-id="2130e-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="2130e-108">.NET Compiler Platform предоставляет платформу для выполнения анализа во время написания кода, а также все функции пользовательского интерфейса Visual Studio для отладки, включая отображение волнистых линий в редакторе, вывод списка ошибок в Visual Studio и отображение значка лампочки, указывающего на наличие предложений и предлагаемых исправлений.</span><span class="sxs-lookup"><span data-stu-id="2130e-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="2130e-109">В этом руководстве описано, как создать **анализатор** и соответствующее **исправление кода** с помощью API Roslyn.</span><span class="sxs-lookup"><span data-stu-id="2130e-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="2130e-110">Анализатор выполняет анализ исходного кода и сообщает о проблеме пользователю.</span><span class="sxs-lookup"><span data-stu-id="2130e-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="2130e-111">При необходимости анализатор может предложить соответствующее исправление для исходного кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="2130e-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="2130e-112">В этом руководстве описано, как создать анализатор, ищущий локальные переменные, которые можно объявить с помощью модификатора `const`, но которые не объявлены.</span><span class="sxs-lookup"><span data-stu-id="2130e-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="2130e-113">Сопутствующее исправление кода добавляет модификатор `const` в эти объявления.</span><span class="sxs-lookup"><span data-stu-id="2130e-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2130e-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2130e-114">Prerequisites</span></span>

- [<span data-ttu-id="2130e-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="2130e-115">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="2130e-116">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2130e-116">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="2130e-117">Необходимо установить **пакет SDK для .NET Compiler Platform** через Visual Studio Installer:</span><span class="sxs-lookup"><span data-stu-id="2130e-117">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="2130e-118">Создать и проверить анализатор можно несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="2130e-118">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="2130e-119">Создайте решение.</span><span class="sxs-lookup"><span data-stu-id="2130e-119">Create the solution.</span></span>
1. <span data-ttu-id="2130e-120">Зарегистрируйте имя и описание анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-120">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="2130e-121">Создайте отчет анализатора о предупреждениях и рекомендациях.</span><span class="sxs-lookup"><span data-stu-id="2130e-121">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="2130e-122">Внедрите исправление кода, чтобы принимать рекомендации.</span><span class="sxs-lookup"><span data-stu-id="2130e-122">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="2130e-123">Улучшите анализ с помощью модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="2130e-123">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="2130e-124">Изучение шаблона анализатора</span><span class="sxs-lookup"><span data-stu-id="2130e-124">Explore the analyzer template</span></span>

<span data-ttu-id="2130e-125">Анализатор сообщает пользователю о любых объявлениях локальной переменной, которые можно преобразовать в локальные константы.</span><span class="sxs-lookup"><span data-stu-id="2130e-125">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="2130e-126">Рассмотрим следующий пример кода:</span><span class="sxs-lookup"><span data-stu-id="2130e-126">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="2130e-127">В приведенном выше коде `x` присваивается значение константы, которое никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="2130e-127">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="2130e-128">Ее можно объявить с помощью модификатора `const`:</span><span class="sxs-lookup"><span data-stu-id="2130e-128">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="2130e-129">Чтобы определить, можно ли изменить переменную на константу, используется синтаксический анализ, анализ константы из выражения инициализатора, а также анализ потока данных, чтобы убедиться, что переменная не записана.</span><span class="sxs-lookup"><span data-stu-id="2130e-129">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="2130e-130">.NET Compiler Platform предоставляет API для упрощения такого анализа.</span><span class="sxs-lookup"><span data-stu-id="2130e-130">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="2130e-131">Сначала нужно создать новый проект C# **анализатора с исправлением кода**.</span><span class="sxs-lookup"><span data-stu-id="2130e-131">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="2130e-132">В Visual Studio последовательно выберите **Файл > Создать > Проект**, чтобы открыть диалоговое окно "Новый проект".</span><span class="sxs-lookup"><span data-stu-id="2130e-132">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="2130e-133">В разделе **Visual C# > Расширяемость** выберите **Analyzer with code fix (.NET Standard)** (Анализатор с исправлением кода (.NET Standard)).</span><span class="sxs-lookup"><span data-stu-id="2130e-133">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="2130e-134">Присвойте проекту имя **MakeConst** и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="2130e-134">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="2130e-135">Анализатор с шаблоном исправления кода создаст три проекта: один содержит анализатор и исправление кода, второй — проект модульного теста и третий — проект VSIX.</span><span class="sxs-lookup"><span data-stu-id="2130e-135">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="2130e-136">Запускаемым проектом по умолчанию является проект VSIX.</span><span class="sxs-lookup"><span data-stu-id="2130e-136">The default startup project is the VSIX project.</span></span> <span data-ttu-id="2130e-137">Нажмите клавишу **F5**, чтобы запустить проект VSIX.</span><span class="sxs-lookup"><span data-stu-id="2130e-137">Press **F5** to start the VSIX project.</span></span> <span data-ttu-id="2130e-138">Это запустит второй экземпляр Visual Studio с загруженным в него анализатором.</span><span class="sxs-lookup"><span data-stu-id="2130e-138">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="2130e-139">Когда вы запустите анализатор, откроется вторая копия Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-139">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="2130e-140">Эта вторая копия использует другой куст реестра для хранения параметров,</span><span class="sxs-lookup"><span data-stu-id="2130e-140">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="2130e-141">что позволяет различить параметры визуальных элементов в обоих копиях Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-141">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="2130e-142">Вы можете выбрать другую тему для экспериментального запуска Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-142">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="2130e-143">Кроме того, не следует перемещать параметры или выполнять вход в учетную запись Visual Studio в экспериментальном экземпляре Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-143">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="2130e-144">Так параметры останутся разными.</span><span class="sxs-lookup"><span data-stu-id="2130e-144">That keeps the settings different.</span></span>

<span data-ttu-id="2130e-145">Во втором экземпляре Visual Studio, который вы только что создали, создайте проект C# консольного приложения (это может быть как проект .NET Core, так и .NET Framework, так как анализаторы работают на уровне источника). Наведите указатель мыши на токен с волнистым подчеркиванием. Появится текст предупреждения от анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-145">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="2130e-146">Шаблон создает анализатор, который выдает предупреждение на каждое объявление типа, где имя типа состоит из букв нижнего регистра, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-146">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Предупреждение от анализатора](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="2130e-148">Также шаблон содержит исправление кода, которое меняет любые буквы нижнего регистра в имени типа на буквы верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="2130e-148">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="2130e-149">Предлагаемые исправления можно просмотреть, щелкнув значок лампочки рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="2130e-149">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="2130e-150">После принятия изменений имя типа и все ссылки на этот тип будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="2130e-150">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="2130e-151">Теперь, когда вы увидели работу начального анализатора, закройте второй экземпляр Visual Studio и вернитесь к проекту анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-151">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="2130e-152">Для тестирования изменений в анализаторе не требуется каждый раз запускать вторую копию Visual Studio,</span><span class="sxs-lookup"><span data-stu-id="2130e-152">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="2130e-153">так как шаблон создает проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="2130e-153">The template also creates a unit test project for you.</span></span> <span data-ttu-id="2130e-154">В этом проекте содержатся два теста.</span><span class="sxs-lookup"><span data-stu-id="2130e-154">That project contains two tests.</span></span> <span data-ttu-id="2130e-155">`TestMethod1` показывает обычный формат теста, при котором анализ кода происходит без активации диагностики.</span><span class="sxs-lookup"><span data-stu-id="2130e-155">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="2130e-156">`TestMethod2` — формат, при котором сначала активируется диагностика, а затем применяется исправление кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-156">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="2130e-157">Во время сборки анализатора и исправления кода вы напишете тесты для проверки разных структур.</span><span class="sxs-lookup"><span data-stu-id="2130e-157">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="2130e-158">Модульные тесты проводятся гораздо быстрее, чем интерактивное тестирование анализаторов в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-158">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="2130e-159">Модульные тесты анализатора — отличный инструмент, если вы знаете, какие конструкции кода должны и не должны запускать анализатор.</span><span class="sxs-lookup"><span data-stu-id="2130e-159">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="2130e-160">В свою очередь запуск анализатора в другой копии Visual Studio позволяет определить и найти конструкции, о которых вы еще не задумывались.</span><span class="sxs-lookup"><span data-stu-id="2130e-160">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="2130e-161">Регистрация анализатора</span><span class="sxs-lookup"><span data-stu-id="2130e-161">Create analyzer registrations</span></span>

<span data-ttu-id="2130e-162">В файле **MakeConstAnalyzer.cs** с помощью шаблона создается начальный класс `DiagnosticAnalyzer`.</span><span class="sxs-lookup"><span data-stu-id="2130e-162">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="2130e-163">В этом начальном анализаторе отображены два важных свойства каждого анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-163">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="2130e-164">В каждом диагностическом анализаторе должен быть указан атрибут `[DiagnosticAnalyzer]`, который описывает язык, на котором он работает.</span><span class="sxs-lookup"><span data-stu-id="2130e-164">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="2130e-165">Каждый диагностический анализатор должен наследоваться от класса <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.</span><span class="sxs-lookup"><span data-stu-id="2130e-165">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="2130e-166">Также в шаблоне отображены базовые функции любого анализатора:</span><span class="sxs-lookup"><span data-stu-id="2130e-166">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="2130e-167">Регистрация действий.</span><span class="sxs-lookup"><span data-stu-id="2130e-167">Register actions.</span></span> <span data-ttu-id="2130e-168">Действия представляют изменения кода, которые запускают анализатор для проверки нарушений.</span><span class="sxs-lookup"><span data-stu-id="2130e-168">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="2130e-169">Когда Visual Studio обнаруживает изменения в коде, которые соответствуют зарегистрированному действию, происходит вызов зарегистрированного метода.</span><span class="sxs-lookup"><span data-stu-id="2130e-169">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="2130e-170">Создание диагностики.</span><span class="sxs-lookup"><span data-stu-id="2130e-170">Create diagnostics.</span></span> <span data-ttu-id="2130e-171">Обнаружив нарушения, анализатор создает объект диагностики, с помощью которого Visual Studio уведомляет пользователя об этом нарушении.</span><span class="sxs-lookup"><span data-stu-id="2130e-171">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="2130e-172">Действия регистрируются в переопределении метода <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2130e-172">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2130e-173">При работе с этим руководстве вы просмотрите **синтаксические узлы** локальных объявлений и узнаете, какие из них имеют значения констант.</span><span class="sxs-lookup"><span data-stu-id="2130e-173">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="2130e-174">Если объявление может быть константой, анализатор создаст диагностику и сформирует отчет.</span><span class="sxs-lookup"><span data-stu-id="2130e-174">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="2130e-175">Сначала обновите константы регистрации и метод `Initialize`, так как константы определяют ваш анализатор MakeConst.</span><span class="sxs-lookup"><span data-stu-id="2130e-175">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="2130e-176">Большинство строковых констант определены в файле строковых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2130e-176">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="2130e-177">Используйте их, чтобы упростить локализацию.</span><span class="sxs-lookup"><span data-stu-id="2130e-177">You should follow that practice for easier localization.</span></span> <span data-ttu-id="2130e-178">Откройте файл **Resources.resx** для проекта анализатора **MakeConst**.</span><span class="sxs-lookup"><span data-stu-id="2130e-178">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="2130e-179">Откроется редактор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2130e-179">This displays the resource editor.</span></span> <span data-ttu-id="2130e-180">Измените строковые ресурсы, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-180">Update the string resources as follows:</span></span>

- <span data-ttu-id="2130e-181">Компонент `AnalyzerTitle` измените на Variable can be made constant (Переменная может быть константой).</span><span class="sxs-lookup"><span data-stu-id="2130e-181">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="2130e-182">Компонент `AnalyzerMessageFormat` измените на Can be made constant (Может быть константой).</span><span class="sxs-lookup"><span data-stu-id="2130e-182">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="2130e-183">Компонент `AnalyzerDescription` измените на Make Constant (Сделать константой).</span><span class="sxs-lookup"><span data-stu-id="2130e-183">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="2130e-184">Также измените раскрывающийся список **модификатора доступа** на `public`.</span><span class="sxs-lookup"><span data-stu-id="2130e-184">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="2130e-185">Это упростит использование этих констант в модульных тестах.</span><span class="sxs-lookup"><span data-stu-id="2130e-185">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="2130e-186">После настройки редактор ресурсов будет иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="2130e-186">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Обновление строковых ресурсов](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="2130e-188">Остальные изменения будут в файле анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-188">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="2130e-189">Откройте файл **MakeConstAnalyzer.cs** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-189">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="2130e-190">Измените зарегистрированное действие на символы на действие на синтаксис.</span><span class="sxs-lookup"><span data-stu-id="2130e-190">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="2130e-191">В методе `MakeConstAnalyzerAnalyzer.Initialize` найдите строку с действием на символы:</span><span class="sxs-lookup"><span data-stu-id="2130e-191">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="2130e-192">Замените ее приведенным ниже кодом:</span><span class="sxs-lookup"><span data-stu-id="2130e-192">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="2130e-193">После этого метод `AnalyzeSymbol` можно удалить.</span><span class="sxs-lookup"><span data-stu-id="2130e-193">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="2130e-194">Этот анализатор проверяет <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, а не операторы <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2130e-194">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="2130e-195">Обратите внимание на то, что `AnalyzeNode` подчеркивается красной волнистой линией,</span><span class="sxs-lookup"><span data-stu-id="2130e-195">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="2130e-196">так как код, который вы только что вставили, ссылается на метод `AnalyzeNode`, который еще не объявлен.</span><span class="sxs-lookup"><span data-stu-id="2130e-196">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="2130e-197">Объявите этот метод, используя приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2130e-197">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="2130e-198">В файле **MakeConstAnalyzer.cs** измените `Category` на Usage (Использование), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-198">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="2130e-199">Поиск локальных объявлений, которые могут быть константами</span><span class="sxs-lookup"><span data-stu-id="2130e-199">Find local declarations that could be const</span></span>

<span data-ttu-id="2130e-200">Теперь мы напишем первую версию метода `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="2130e-200">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="2130e-201">Он должен найти одно локальное объявление, которое может быть `const`, но таковым не является. Пример приведен ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-201">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="2130e-202">Сначала найдите локальные объявления.</span><span class="sxs-lookup"><span data-stu-id="2130e-202">The first step is to find local declarations.</span></span> <span data-ttu-id="2130e-203">Добавьте приведенный ниже код в `AnalyzeNode` в файле **MakeConstAnalyzer.cs**:</span><span class="sxs-lookup"><span data-stu-id="2130e-203">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="2130e-204">Это приведение всегда завершается успешно, так как ваш анализатор зарегистрирован для отслеживания изменений только локальных объявлений.</span><span class="sxs-lookup"><span data-stu-id="2130e-204">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="2130e-205">Другие типы узлов не вызывают метод `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="2130e-205">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="2130e-206">Затем проверьте объявление на наличие модификаторов `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-206">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="2130e-207">Если они есть, сразу же выполните возврат.</span><span class="sxs-lookup"><span data-stu-id="2130e-207">If you find them, return immediately.</span></span> <span data-ttu-id="2130e-208">Приведенный ниже код ищет модификаторы `const` в локальном объявлении:</span><span class="sxs-lookup"><span data-stu-id="2130e-208">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="2130e-209">В конце проверьте, может ли переменная быть `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-209">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="2130e-210">Это означает, что она не может быть назначена после инициализации.</span><span class="sxs-lookup"><span data-stu-id="2130e-210">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="2130e-211">Выполните семантический анализ с помощью <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span><span class="sxs-lookup"><span data-stu-id="2130e-211">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="2130e-212">Используйте аргумент `context`, чтобы определить, можно ли объявление локальной переменной сделать `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-212">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="2130e-213"><xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> представляет все семантические сведения в одном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="2130e-213">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents of all semantic information in a single source file.</span></span> <span data-ttu-id="2130e-214">См. дополнительные сведения о [семантических моделях](../work-with-semantics.md).</span><span class="sxs-lookup"><span data-stu-id="2130e-214">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="2130e-215">С помощью <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> выполните анализ потока данных на операторе локального объявления.</span><span class="sxs-lookup"><span data-stu-id="2130e-215">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="2130e-216">Затем, используя результаты этого анализа потока данных, убедитесь, что в локальную переменную не записывается новое значение где-либо еще.</span><span class="sxs-lookup"><span data-stu-id="2130e-216">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="2130e-217">Вызовите метод расширения <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A>, чтобы извлечь <xref:Microsoft.CodeAnalysis.ILocalSymbol> переменной и убедиться, что она не содержится в коллекции <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> из анализа потока данных.</span><span class="sxs-lookup"><span data-stu-id="2130e-217">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="2130e-218">Добавьте в конце метода `AnalyzeNode` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2130e-218">Add the following code to the end of the `AnalyzeNode` method:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="2130e-219">Этот код гарантирует, что переменная не изменена и может быть `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-219">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="2130e-220">Теперь мы активируем диагностику.</span><span class="sxs-lookup"><span data-stu-id="2130e-220">It's time to raise the diagnostic.</span></span> <span data-ttu-id="2130e-221">Добавьте приведенный ниже код в последнюю строку метода `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="2130e-221">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="2130e-222">Чтобы проверить состояние, запустите анализатор, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="2130e-222">You can check your progress by pressing **F5** to run your analyzer.</span></span> <span data-ttu-id="2130e-223">Загрузите консольное приложение, созданное ранее, и добавьте приведенный ниже код теста:</span><span class="sxs-lookup"><span data-stu-id="2130e-223">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="2130e-224">Появится лампочка и анализатор выдаст отчет с диагностическими сведениями.</span><span class="sxs-lookup"><span data-stu-id="2130e-224">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="2130e-225">При этом поведение лампочки по-прежнему основано на исправлении кода, сгенерированном шаблоном, указывая на то, что можно использовать буквы верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="2130e-225">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="2130e-226">В следующем разделе показано, как написать исправление кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-226">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="2130e-227">Написание исправления кода</span><span class="sxs-lookup"><span data-stu-id="2130e-227">Write the code fix</span></span>

<span data-ttu-id="2130e-228">Анализатор поддерживает одно или несколько исправлений кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-228">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="2130e-229">Исправление кода определяет, какие правки нужно внести для решения обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="2130e-229">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="2130e-230">Исправление кода вашего анализатора предоставляет код с ключевым словом const:</span><span class="sxs-lookup"><span data-stu-id="2130e-230">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="2130e-231">Пользователь выбирает исправление в интерфейсе лампочки в редакторе, а Visual Studio изменяет код.</span><span class="sxs-lookup"><span data-stu-id="2130e-231">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="2130e-232">Откройте файл **MakeConstCodeFixProvider.cs**, добавленный шаблоном.</span><span class="sxs-lookup"><span data-stu-id="2130e-232">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="2130e-233">Это исправление уже привязано к идентификатору диагностики вашего анализатора, но оно пока не реализует преобразование кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-233">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="2130e-234">Сначала удалите часть кода шаблона.</span><span class="sxs-lookup"><span data-stu-id="2130e-234">First you should remove some of the template code.</span></span> <span data-ttu-id="2130e-235">Измените строку заголовка на Make constant (Сделать константой):</span><span class="sxs-lookup"><span data-stu-id="2130e-235">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="2130e-236">Затем удалите метод `MakeUppercaseAsync`.</span><span class="sxs-lookup"><span data-stu-id="2130e-236">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="2130e-237">Он больше не применяется.</span><span class="sxs-lookup"><span data-stu-id="2130e-237">It no longer applies.</span></span>

<span data-ttu-id="2130e-238">Все поставщики исправлений кода являются производными от <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span><span class="sxs-lookup"><span data-stu-id="2130e-238">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="2130e-239">и переопределяют <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> на сообщение о доступных исправлениях.</span><span class="sxs-lookup"><span data-stu-id="2130e-239">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="2130e-240">В <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> измените тип узла-предка на `RegisterCodeFixesAsync` в соответствии с диагностикой:</span><span class="sxs-lookup"><span data-stu-id="2130e-240">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="2130e-241">Затем, чтобы зарегистрировать исправление кода, измените последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="2130e-241">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="2130e-242">Исправление создаст документ, полученный после добавления модификатора `const` к существующему объявлению:</span><span class="sxs-lookup"><span data-stu-id="2130e-242">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="2130e-243">Под символом `MakeConstAsync` появятся красные волнистые линии.</span><span class="sxs-lookup"><span data-stu-id="2130e-243">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="2130e-244">Добавьте объявление в `MakeConstAsync`, например как указано ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-244">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="2130e-245">Новый метод `MakeConstAsync` преобразует <xref:Microsoft.CodeAnalysis.Document> исходного файла пользователя в новый экземпляр <xref:Microsoft.CodeAnalysis.Document>, содержащий объявление `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-245">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="2130e-246">Создайте новый токен ключевого слова `const` и вставьте его перед оператором объявления.</span><span class="sxs-lookup"><span data-stu-id="2130e-246">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="2130e-247">Не забудьте сначала удалить все элементы trivia из первого оператора объявления и подключить к токену `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-247">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="2130e-248">Добавьте следующий код в метод `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="2130e-248">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="2130e-249">Затем добавьте токен `const` к объявлению с помощью приведенного ниже кода:</span><span class="sxs-lookup"><span data-stu-id="2130e-249">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="2130e-250">Отформатируйте новое объявление в соответствии с правилами форматирования C#.</span><span class="sxs-lookup"><span data-stu-id="2130e-250">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="2130e-251">Форматирование изменений в соответствии с существующим кодом упрощает работу.</span><span class="sxs-lookup"><span data-stu-id="2130e-251">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="2130e-252">Добавьте приведенный ниже оператор сразу после существующего кода:</span><span class="sxs-lookup"><span data-stu-id="2130e-252">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="2130e-253">Для выполнения этого кода требуется новое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2130e-253">A new namespace is required for this code.</span></span> <span data-ttu-id="2130e-254">Добавьте следующий оператор `using` в начало файла:</span><span class="sxs-lookup"><span data-stu-id="2130e-254">Add the following `using` statement to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="2130e-255">В конце нужно внести правки.</span><span class="sxs-lookup"><span data-stu-id="2130e-255">The final step is to make your edit.</span></span> <span data-ttu-id="2130e-256">Для этого выполните эти три шага:</span><span class="sxs-lookup"><span data-stu-id="2130e-256">There are three steps to this process:</span></span>

1. <span data-ttu-id="2130e-257">Получите дескриптор существующего документа.</span><span class="sxs-lookup"><span data-stu-id="2130e-257">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="2130e-258">Создайте документ, заменив существующее объявление на новое.</span><span class="sxs-lookup"><span data-stu-id="2130e-258">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="2130e-259">Верните новый документ.</span><span class="sxs-lookup"><span data-stu-id="2130e-259">Return the new document.</span></span>

<span data-ttu-id="2130e-260">Добавьте в конце метода `MakeConstAsync` приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2130e-260">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="2130e-261">Ваше исправление кода готово.</span><span class="sxs-lookup"><span data-stu-id="2130e-261">Your code fix is ready to try.</span></span>  <span data-ttu-id="2130e-262">Нажмите клавишу F5, чтобы запустить проект анализатора во втором экземпляре Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-262">Press F5 to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="2130e-263">Во втором экземпляре Visual Studio создайте проект C# консольного приложения и добавьте несколько объявлений локальной переменной, инициализированных со значениями константы в методе main.</span><span class="sxs-lookup"><span data-stu-id="2130e-263">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="2130e-264">Они будут отмечены как предупреждения. См. пример ниже.</span><span class="sxs-lookup"><span data-stu-id="2130e-264">You'll see that they are reported as warnings as below.</span></span>

![Предупреждение о назначении константы](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="2130e-266">Мы уже много сделали.</span><span class="sxs-lookup"><span data-stu-id="2130e-266">You've made a lot of progress.</span></span> <span data-ttu-id="2130e-267">Объявления, которые могут быть `const`, подчеркнуты волнистой линией.</span><span class="sxs-lookup"><span data-stu-id="2130e-267">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="2130e-268">Но нам еще нужно с ними поработать.</span><span class="sxs-lookup"><span data-stu-id="2130e-268">But there is still work to do.</span></span> <span data-ttu-id="2130e-269">Здесь следует добавить `const` в объявления `i`, затем `j` и `k`.</span><span class="sxs-lookup"><span data-stu-id="2130e-269">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="2130e-270">Но если вы добавите модификатор `const` в обратном порядке, начиная с `k`, анализатор выдаст ошибки: `k` не может быть объявлен как `const`, пока `i` и `j` не являются `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-270">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="2130e-271">Нужно выполнить дополнительный анализ, чтобы убедиться, что переменные можно объявить и инициализировать различными путями.</span><span class="sxs-lookup"><span data-stu-id="2130e-271">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="2130e-272">Выполнение теста, управляемого данными</span><span class="sxs-lookup"><span data-stu-id="2130e-272">Build data driven tests</span></span>

<span data-ttu-id="2130e-273">Анализатор и исправление кода работают на простом примере одного объявления, которое может быть константой.</span><span class="sxs-lookup"><span data-stu-id="2130e-273">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="2130e-274">Есть множество возможных операторов объявления, где они выдают ошибки.</span><span class="sxs-lookup"><span data-stu-id="2130e-274">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="2130e-275">В этих ситуациях можно обратиться к библиотеке модульных тестов, созданной шаблоном.</span><span class="sxs-lookup"><span data-stu-id="2130e-275">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="2130e-276">Это гораздо быстрее, чем каждый раз запускать вторую копию Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2130e-276">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="2130e-277">Откройте файл **MakeConstUnitTests.cs** в проекте модульного теста.</span><span class="sxs-lookup"><span data-stu-id="2130e-277">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="2130e-278">В нем созданы два теста по общим шаблонам для анализатора и для модульного теста исправления кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-278">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="2130e-279">Метод `TestMethod1` гарантирует, что анализатор не выдаст отчет о диагностике, когда это не нужно.</span><span class="sxs-lookup"><span data-stu-id="2130e-279">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="2130e-280">Метод `TestMethod2` выдает отчет о диагностике и запускает исправление кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-280">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="2130e-281">Код почти каждого теста вашего анализатора работает по одному из этих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2130e-281">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="2130e-282">Сначала переделайте эти тесты в тесты, управляемые данными.</span><span class="sxs-lookup"><span data-stu-id="2130e-282">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="2130e-283">Так будет проще создавать новые тесты, добавляя новые строковые константы для представления различных входных данных.</span><span class="sxs-lookup"><span data-stu-id="2130e-283">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="2130e-284">Для повышения эффективности сначала выполните рефакторинг двух тестов в тесты, управляемые данными.</span><span class="sxs-lookup"><span data-stu-id="2130e-284">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="2130e-285">Затем можно определять несколько строковых констант для каждого нового теста.</span><span class="sxs-lookup"><span data-stu-id="2130e-285">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="2130e-286">Во время рефакторинга переименуйте оба метода.</span><span class="sxs-lookup"><span data-stu-id="2130e-286">While your refactoring, rename both methods to better names.</span></span> <span data-ttu-id="2130e-287">Замените `TestMethod1` тестом, который гарантирует отсутствие диагностики:</span><span class="sxs-lookup"><span data-stu-id="2130e-287">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="2130e-288">Вы можете создать новую строку данных для теста. Для этого определите фрагмент кода, который не должен вызывать предупреждение диагностики.</span><span class="sxs-lookup"><span data-stu-id="2130e-288">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="2130e-289">Эта перегрузка `VerifyCSharpDiagnostic` передается, если для фрагмента исходного кода диагностика не вызывалась.</span><span class="sxs-lookup"><span data-stu-id="2130e-289">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="2130e-290">Затем замените `TestMethod2` этим тестом, который гарантирует вызов диагностики, а также то, что исправление применяется к этому фрагменту исходного кода:</span><span class="sxs-lookup"><span data-stu-id="2130e-290">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

<span data-ttu-id="2130e-291">Приведенный выше код также вносит изменения в код, который компилирует ожидаемый результат диагностики.</span><span class="sxs-lookup"><span data-stu-id="2130e-291">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="2130e-292">Для этого используются открытые константы, зарегистрированные в анализаторе `MakeConst`.</span><span class="sxs-lookup"><span data-stu-id="2130e-292">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="2130e-293">Также используются две строковые константы для введенного и исправленного источника.</span><span class="sxs-lookup"><span data-stu-id="2130e-293">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="2130e-294">Добавьте приведенные ниже строковые константы в класс `UnitTest`:</span><span class="sxs-lookup"><span data-stu-id="2130e-294">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="2130e-295">Чтобы убедиться в том, что они переданы, запустите оба теста.</span><span class="sxs-lookup"><span data-stu-id="2130e-295">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="2130e-296">Откройте **обозреватель тестов** в Visual Studio, последовательно выбрав **Тест** > **Windows** > **Обозреватель тестов**.</span><span class="sxs-lookup"><span data-stu-id="2130e-296">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span>  <span data-ttu-id="2130e-297">Щелкните ссылку **Выполнить все**.</span><span class="sxs-lookup"><span data-stu-id="2130e-297">The press the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="2130e-298">Создание тестов для допустимых объявлений</span><span class="sxs-lookup"><span data-stu-id="2130e-298">Create tests for valid declarations</span></span>

<span data-ttu-id="2130e-299">Как правило, анализаторы должны завершать работу как можно быстрее, выполняя минимум операций.</span><span class="sxs-lookup"><span data-stu-id="2130e-299">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="2130e-300">Когда пользователь правит код, Visual Studio вызывает зарегистрированные анализаторы.</span><span class="sxs-lookup"><span data-stu-id="2130e-300">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="2130e-301">Основным требованием здесь является скорость реагирования.</span><span class="sxs-lookup"><span data-stu-id="2130e-301">Responsiveness is a key requirement.</span></span> <span data-ttu-id="2130e-302">Существует несколько тестовых случаев для кода, который не должен вызывать диагностику.</span><span class="sxs-lookup"><span data-stu-id="2130e-302">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="2130e-303">Анализатор уже обрабатывает один из них — тот, при котором переменная присваивается после инициализации.</span><span class="sxs-lookup"><span data-stu-id="2130e-303">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="2130e-304">Чтобы воспроизвести этот случай, добавьте приведенную ниже строковую константу в тест:</span><span class="sxs-lookup"><span data-stu-id="2130e-304">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="2130e-305">Затем добавьте строку данных, как показано во фрагменте ниже:</span><span class="sxs-lookup"><span data-stu-id="2130e-305">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="2130e-306">Этот тест также проходит.</span><span class="sxs-lookup"><span data-stu-id="2130e-306">This test passes as well.</span></span> <span data-ttu-id="2130e-307">Далее добавьте константы для условий, которые еще не обработаны:</span><span class="sxs-lookup"><span data-stu-id="2130e-307">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="2130e-308">Объявления, которые представляют `const`, так как они уже являются константами:</span><span class="sxs-lookup"><span data-stu-id="2130e-308">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="2130e-309">Объявления, у которых нет инициализатора, так как нет соответствующего значения:</span><span class="sxs-lookup"><span data-stu-id="2130e-309">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="2130e-310">Объявления, у которых инициализатор не является константой, так как они не могут быть константами времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="2130e-310">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="2130e-311">Трудность заключается еще в том, что в C# допускается несколько объявлений, работающих как один оператор.</span><span class="sxs-lookup"><span data-stu-id="2130e-311">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="2130e-312">Рассмотрите приведенную ниже строковую константу тестового случая:</span><span class="sxs-lookup"><span data-stu-id="2130e-312">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="2130e-313">Переменная `i` может быть константой, а переменная `j` — нет.</span><span class="sxs-lookup"><span data-stu-id="2130e-313">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="2130e-314">Поэтому этот оператор не может быть объявлением константы.</span><span class="sxs-lookup"><span data-stu-id="2130e-314">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="2130e-315">Добавьте объявления `DataRow` для всех тестов:</span><span class="sxs-lookup"><span data-stu-id="2130e-315">Add the `DataRow` declarations for all these tests:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="2130e-316">Снова запустите тесты. Произойдет сбой в новых тестовых случаях.</span><span class="sxs-lookup"><span data-stu-id="2130e-316">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="2130e-317">Обновление анализатора для пропуска верных объявлений</span><span class="sxs-lookup"><span data-stu-id="2130e-317">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="2130e-318">Чтобы отфильтровать код, который соответствует условиям, необходимо преобразовать метод `AnalyzeNode` анализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-318">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="2130e-319">Эти условия связаны между собой, и изменения в одном из них будут применены ко всем.</span><span class="sxs-lookup"><span data-stu-id="2130e-319">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="2130e-320">Внесите следующие изменения в `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="2130e-320">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="2130e-321">Для объявления одной переменной был выполнен семантический анализ.</span><span class="sxs-lookup"><span data-stu-id="2130e-321">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="2130e-322">Этот код должен находиться в цикле `foreach`, который проверяет все переменные, объявленные в одном и том же операторе.</span><span class="sxs-lookup"><span data-stu-id="2130e-322">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="2130e-323">Каждая объявленная переменная должна иметь инициализатор.</span><span class="sxs-lookup"><span data-stu-id="2130e-323">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="2130e-324">Каждый инициализатор переменной должен быть константой времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="2130e-324">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="2130e-325">В методе `AnalyzeNode` замените исходный семантический анализ:</span><span class="sxs-lookup"><span data-stu-id="2130e-325">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="2130e-326">приведенным ниже фрагментом кода:</span><span class="sxs-lookup"><span data-stu-id="2130e-326">with the following code snippet:</span></span>

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

<span data-ttu-id="2130e-327">Первый цикл `foreach` проверяет каждое объявление переменной с помощью синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="2130e-327">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="2130e-328">В первой проверке подтверждается наличие инициализатора.</span><span class="sxs-lookup"><span data-stu-id="2130e-328">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="2130e-329">Во второй — что этот инициализатор является константой.</span><span class="sxs-lookup"><span data-stu-id="2130e-329">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="2130e-330">Во втором цикле запускается исходный семантический анализ.</span><span class="sxs-lookup"><span data-stu-id="2130e-330">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="2130e-331">Семантические проверки проходят в отдельных циклах, так как они серьезно влияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="2130e-331">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="2130e-332">Снова запустите тест. Все проверки должны быть пройдены.</span><span class="sxs-lookup"><span data-stu-id="2130e-332">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="2130e-333">Финальные штрихи</span><span class="sxs-lookup"><span data-stu-id="2130e-333">Add the final polish</span></span>

<span data-ttu-id="2130e-334">Вы почти у цели.</span><span class="sxs-lookup"><span data-stu-id="2130e-334">You're almost done.</span></span> <span data-ttu-id="2130e-335">Анализатор должен обработать еще несколько условий.</span><span class="sxs-lookup"><span data-stu-id="2130e-335">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="2130e-336">Пока пользователь пишет код, Visual Studio вызывает анализаторы.</span><span class="sxs-lookup"><span data-stu-id="2130e-336">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="2130e-337">Часто бывает так, что анализатор вызван для кода, который не компилируется.</span><span class="sxs-lookup"><span data-stu-id="2130e-337">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="2130e-338">Метод `AnalyzeNode` диагностического анализатора не проверяет, можно ли преобразовать значение константы в тип переменной.</span><span class="sxs-lookup"><span data-stu-id="2130e-338">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="2130e-339">Поэтому в текущей реализации все неверные объявления, такие как int i = "abc", преобразуются в локальные константы.</span><span class="sxs-lookup"><span data-stu-id="2130e-339">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="2130e-340">Добавьте исходную строковую константу в это условие:</span><span class="sxs-lookup"><span data-stu-id="2130e-340">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="2130e-341">Кроме того, ссылочные типы обрабатываются неправильно.</span><span class="sxs-lookup"><span data-stu-id="2130e-341">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="2130e-342">Единственное допустимое значение константы для ссылочного типа — `null`, кроме случаев с <xref:System.String?displayProperty=nameWithType>, в которых работают строковые литералы.</span><span class="sxs-lookup"><span data-stu-id="2130e-342">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="2130e-343">Другими словами, `const string s = "abc"` является допустимым, а `const object s = "abc"` — нет.</span><span class="sxs-lookup"><span data-stu-id="2130e-343">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="2130e-344">Этот фрагмент кода проверяет это условие:</span><span class="sxs-lookup"><span data-stu-id="2130e-344">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="2130e-345">Чтобы убедиться в том, что можно создать объявление константы для строки, добавьте еще один тест.</span><span class="sxs-lookup"><span data-stu-id="2130e-345">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="2130e-346">В приведенным ниже фрагменте кода определен как код, вызывающий диагностику, так и код после исправления:</span><span class="sxs-lookup"><span data-stu-id="2130e-346">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="2130e-347">Если переменная объявлена с ключевым словом `var`, исправление выдает объявление `const var`, которое не поддерживается в C#.</span><span class="sxs-lookup"><span data-stu-id="2130e-347">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="2130e-348">Чтобы исправить эту ошибку, исправление должно заменить ключевое слово `var` именем выведенного типа:</span><span class="sxs-lookup"><span data-stu-id="2130e-348">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="2130e-349">Эти изменения обновят объявления строк данных для обоих тестов.</span><span class="sxs-lookup"><span data-stu-id="2130e-349">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="2130e-350">В приведенном ниже коде показаны тесты со всеми атрибутами строк данных:</span><span class="sxs-lookup"><span data-stu-id="2130e-350">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="2130e-351">К счастью, все вышеперечисленные ошибки можно устранить с помощью методов, которые вы только что изучили.</span><span class="sxs-lookup"><span data-stu-id="2130e-351">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="2130e-352">Чтобы исправить первую ошибку, сначала откройте файл **DiagnosticAnalyzer.cs** и найдите цикл foreach, в котором проверяются инициализаторы локальных объявлений. Им должны быть назначены значения констант.</span><span class="sxs-lookup"><span data-stu-id="2130e-352">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="2130e-353">Сразу же, _до_ выполнения цикла foreach, вызовите `context.SemanticModel.GetTypeInfo()`, чтобы извлечь подробные сведения об объявленном типе из локального объявления:</span><span class="sxs-lookup"><span data-stu-id="2130e-353">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="2130e-354">Затем проверьте каждый инициализатор внутри цикла `foreach`, чтобы убедиться в том, что его можно преобразовать в тип переменной.</span><span class="sxs-lookup"><span data-stu-id="2130e-354">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="2130e-355">Убедившись в том, что инициализатор является константой, добавьте приведенную ниже проверку:</span><span class="sxs-lookup"><span data-stu-id="2130e-355">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="2130e-356">Следующее изменение основано на последнем.</span><span class="sxs-lookup"><span data-stu-id="2130e-356">The next change builds upon the last one.</span></span> <span data-ttu-id="2130e-357">Перед закрывающей фигурной скобкой первого цикла foreach добавьте приведенный ниже код. Он проверит тип локального объявления, когда константа является строкой или имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="2130e-357">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

<span data-ttu-id="2130e-358">Необходимо заменить ключевое слово var правильным именем типа в вашем поставщике исправлений кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-358">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="2130e-359">Вернитесь к файлу **CodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="2130e-359">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="2130e-360">Код, который вы добавите, выполняет следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="2130e-360">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="2130e-361">Проверяет, является ли объявление `var`, если да:</span><span class="sxs-lookup"><span data-stu-id="2130e-361">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="2130e-362">Создает тип для выводимого типа.</span><span class="sxs-lookup"><span data-stu-id="2130e-362">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="2130e-363">Проверяет, что объявление типа не является псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="2130e-363">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="2130e-364">Если это так, можно объявить `const var`.</span><span class="sxs-lookup"><span data-stu-id="2130e-364">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="2130e-365">Проверяет, что `var` не является именем типа в программе</span><span class="sxs-lookup"><span data-stu-id="2130e-365">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="2130e-366">(если это так, `const var` является допустимым).</span><span class="sxs-lookup"><span data-stu-id="2130e-366">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="2130e-367">Упрощает полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="2130e-367">Simplify the full type name</span></span>

<span data-ttu-id="2130e-368">Кажется, что здесь довольно много кода.</span><span class="sxs-lookup"><span data-stu-id="2130e-368">That sounds like a lot of code.</span></span> <span data-ttu-id="2130e-369">Но это не так.</span><span class="sxs-lookup"><span data-stu-id="2130e-369">It's not.</span></span> <span data-ttu-id="2130e-370">Замените строку, которая объявляет и инициализирует `newLocal` приведенным ниже кодом.</span><span class="sxs-lookup"><span data-stu-id="2130e-370">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="2130e-371">Он выполняется сразу после инициализации `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="2130e-371">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="2130e-372">Чтобы использовать тип <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>, потребуется добавить один оператор `using`:</span><span class="sxs-lookup"><span data-stu-id="2130e-372">You'll need to add one `using` statement to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="2130e-373">Запустите тесты. Они все должны быть пройдены.</span><span class="sxs-lookup"><span data-stu-id="2130e-373">Run your tests, and they should all pass.</span></span> <span data-ttu-id="2130e-374">Можете поздравить себя, запустив готовый анализатор.</span><span class="sxs-lookup"><span data-stu-id="2130e-374">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="2130e-375">Чтобы запустить проект анализатора во втором экземпляре Visual Studio с загруженным расширением предварительной версии Roslyn, нажмите клавиши Ctrl+F5.</span><span class="sxs-lookup"><span data-stu-id="2130e-375">Press Ctrl+F5 to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="2130e-376">Во втором экземпляре Visual Studio создайте новый проект C# консольного приложения и добавьте `int x = "abc";` в метод main.</span><span class="sxs-lookup"><span data-stu-id="2130e-376">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="2130e-377">Так как первая ошибка была исправлена, для объявления локальной переменной не должно выдаваться предупреждение (хотя есть ошибка компилятора, как и предполагалось).</span><span class="sxs-lookup"><span data-stu-id="2130e-377">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="2130e-378">Затем добавьте `object s = "abc";` в метод main.</span><span class="sxs-lookup"><span data-stu-id="2130e-378">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="2130e-379">Так как вторая ошибка была исправлена, не должно быть никаких предупреждений.</span><span class="sxs-lookup"><span data-stu-id="2130e-379">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="2130e-380">Наконец, добавьте другую локальную переменную, использующую ключевое слово `var`.</span><span class="sxs-lookup"><span data-stu-id="2130e-380">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="2130e-381">Внизу слева появится предупреждение и предложение исправлений.</span><span class="sxs-lookup"><span data-stu-id="2130e-381">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="2130e-382">Наведите курсор редактора на волнистую линию и нажмите клавиши Ctrl+.</span><span class="sxs-lookup"><span data-stu-id="2130e-382">Move the editor caret over the squiggly underline and press Ctrl+.</span></span> <span data-ttu-id="2130e-383">Отобразятся предложенные исправления.</span><span class="sxs-lookup"><span data-stu-id="2130e-383">to display the suggested code fix.</span></span> <span data-ttu-id="2130e-384">Обратите внимание, что после выбора исправления ключевое слово var теперь обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="2130e-384">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="2130e-385">В конце добавьте приведенный ниже код:</span><span class="sxs-lookup"><span data-stu-id="2130e-385">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="2130e-386">После этого только две переменные будут подчеркнуты красными волнистыми линиями.</span><span class="sxs-lookup"><span data-stu-id="2130e-386">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="2130e-387">Добавьте `const` в `i` и `j`. Появится предупреждение, указывающее на то, что `k` может быть `const`.</span><span class="sxs-lookup"><span data-stu-id="2130e-387">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="2130e-388">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="2130e-388">Congratulations!</span></span> <span data-ttu-id="2130e-389">Вы создали свое первое расширение .NET Compiler Platform, которое выполняет анализ кода в режиме реального времени, находит проблемы и быстро их исправляет.</span><span class="sxs-lookup"><span data-stu-id="2130e-389">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="2130e-390">Кроме того, вы изучили множество API, входящих в пакет SDK .NET Compiler Platform (API Roslyn).</span><span class="sxs-lookup"><span data-stu-id="2130e-390">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="2130e-391">Вы можете сравнить результат своей работы с [готовым примером](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) в нашем репозитории в GitHub.</span><span class="sxs-lookup"><span data-stu-id="2130e-391">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="2130e-392">Другие источники</span><span class="sxs-lookup"><span data-stu-id="2130e-392">Other resources</span></span>

- [<span data-ttu-id="2130e-393">Начало работы с функциями синтаксического анализа</span><span class="sxs-lookup"><span data-stu-id="2130e-393">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="2130e-394">Начало работы с семантическим анализом</span><span class="sxs-lookup"><span data-stu-id="2130e-394">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
