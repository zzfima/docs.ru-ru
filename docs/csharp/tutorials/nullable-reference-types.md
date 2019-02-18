---
title: Разработка с использованием ссылочных типов, допускающих значение null
description: В этом расширенном руководстве содержатся общие сведения о ссылочных типах, допускающих значение null. Вы научитесь выражать проектный замысел относительно того, когда ссылочные значения могут иметь значение null, и используете компилятор, который будет применять соответствующее поведение, когда они не могут иметь значение null.
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: 535efcdc303c17a55f6a4054ea3f5e5ed87e5f28
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092206"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="f7d67-104">Учебник. Четкое выражение проектного замысла с помощью ссылочных типов, допускающих и не допускающих значение null</span><span class="sxs-lookup"><span data-stu-id="f7d67-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="f7d67-105">В C# 8 вводятся **ссылочные типы, допускающие значение null**, которые дополняют ссылочные типы таким же образом, как типы значений, допускающие значение null, дополняют другие типы значений.</span><span class="sxs-lookup"><span data-stu-id="f7d67-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="f7d67-106">Чтобы объявить переменную как имеющую **ссылочный тип, допускающий значение null**, добавьте `?` к типу.</span><span class="sxs-lookup"><span data-stu-id="f7d67-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="f7d67-107">Например, `string?` соответствует типу `string`, допускающему значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="f7d67-108">Эти новые типы можно использовать для более четкого выражения проектного замысла: некоторые переменные *всегда должны содержать значение*, а в других *они могут отсутствовать*.</span><span class="sxs-lookup"><span data-stu-id="f7d67-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="f7d67-109">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="f7d67-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f7d67-110">Внедрять в проекты ссылочные типы, допускающие и не допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="f7d67-111">Включать в коде проверку ссылочных типов, допускающих значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="f7d67-112">Писать код, в котором компилятор принудительно применяет эти проектные решения.</span><span class="sxs-lookup"><span data-stu-id="f7d67-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="f7d67-113">Использовать ссылочный тип, допускающий значение null, в собственных проектах.</span><span class="sxs-lookup"><span data-stu-id="f7d67-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7d67-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f7d67-114">Prerequisites</span></span>

<span data-ttu-id="f7d67-115">Вам нужно настроить на компьютере выполнение .NET Core, включая бета-компилятор C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f7d67-115">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="f7d67-116">Бета-компилятор C# 8 доступен в [предварительной версии 1 Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) или [в предварительной версии 1 .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="f7d67-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="f7d67-117">В этом руководстве предполагается, что вы знакомы с C# и .NET, включая Visual Studio или .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="f7d67-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="f7d67-118">Внедрение в проекты ссылочных типов, допускающих значение null</span><span class="sxs-lookup"><span data-stu-id="f7d67-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="f7d67-119">В этом руководстве вы создадите библиотеку, моделирующую выполнение опроса.</span><span class="sxs-lookup"><span data-stu-id="f7d67-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="f7d67-120">Код использует оба ссылочных типа (допускающий и не допускающий значение null) для представления реальных понятий.</span><span class="sxs-lookup"><span data-stu-id="f7d67-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="f7d67-121">Вопросы в опросе никогда не могут принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-121">The survey questions can never be null.</span></span> <span data-ttu-id="f7d67-122">Респондент может предпочесть не отвечать на вопрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="f7d67-123">В этом случае ответы могут принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-123">The responses might be null in this case.</span></span>

<span data-ttu-id="f7d67-124">Код, который вы напишете для этого примера, выражает это намерение, а компилятор применяет его.</span><span class="sxs-lookup"><span data-stu-id="f7d67-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="f7d67-125">Создание приложения и включение ссылочных типов, допускающих значение null</span><span class="sxs-lookup"><span data-stu-id="f7d67-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="f7d67-126">Создайте новое консольное приложение в Visual Studio или из командной строки с помощью `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="f7d67-127">Присвойте приложению имя `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="f7d67-128">После создания приложения вам потребуется включить функции бета-версии C# 8.</span><span class="sxs-lookup"><span data-stu-id="f7d67-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="f7d67-129">Откройте файл `csproj` и добавьте элемент `LangVersion` в элемент `PropertyGroup`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-129">Open the `csproj` file, and add a `LangVersion` element to the `PropertyGroup` element:</span></span>

```xml
<LangVersion>8.0</LangVersion>
```

<span data-ttu-id="f7d67-130">Кроме того, можно использовать свойства проекта Visual Studio, чтобы включить C# 8.</span><span class="sxs-lookup"><span data-stu-id="f7d67-130">Alternatively, you can use the Visual Studio project properties to enable C# 8.</span></span> <span data-ttu-id="f7d67-131">В обозревателе решений щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f7d67-131">In Solution Explorer, right click on the project node, select **Properties**.</span></span> <span data-ttu-id="f7d67-132">Перейдите на вкладку **Сборка** и нажмите кнопку **Дополнительно...** В раскрывающемся списке языковых версий выберите **C# 8.0 (beta)** (C# 8.0 (бета-версия)).</span><span class="sxs-lookup"><span data-stu-id="f7d67-132">Then, select the **build** tab, and click **Advanced...**. In the dropdown for language version, select **C# 8.0 (beta)**.</span></span>

<span data-ttu-id="f7d67-133">Необходимо выбрать функцию **ссылочных типов, допускающих значение null**, даже в проектах C# 8.</span><span class="sxs-lookup"><span data-stu-id="f7d67-133">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="f7d67-134">Это связано с тем, что когда эта функция будет включена, существующие объявления ссылочных переменных становятся **ссылочными типами, допускающими значение null**.</span><span class="sxs-lookup"><span data-stu-id="f7d67-134">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="f7d67-135">Хотя это решение поможет найти проблемы, где существующий код может не иметь правильных проверок нулевых значений, оно может не точно отражать исходное намерение проекта.</span><span class="sxs-lookup"><span data-stu-id="f7d67-135">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="f7d67-136">Включите функцию с помощью новой директивы pragma:</span><span class="sxs-lookup"><span data-stu-id="f7d67-136">You turn on the feature with a new pragma:</span></span>

```csharp
#nullable enable
```

<span data-ttu-id="f7d67-137">Предыдущую директиву pragma можно добавить в любом месте исходного файла, после чего функция ссылочного типа, допускающего значение null, будет включена.</span><span class="sxs-lookup"><span data-stu-id="f7d67-137">You can add the preceding pragma anywhere in a source file, and the nullable reference type feature is turned on from that point.</span></span> <span data-ttu-id="f7d67-138">Рragma также поддерживает аргумент `disable` для отключения этой функции.</span><span class="sxs-lookup"><span data-stu-id="f7d67-138">The pragma also supports the `disable` argument to turn off the feature.</span></span>

<span data-ttu-id="f7d67-139">Можно также включить **ссылочные типы, допускающие значение null**, для всего проекта, добавив следующий элемент в CSPROJ-файл, например, сразу после элемента `LangVersion`, который включает C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f7d67-139">You can also turn on **nullable reference types** for an entire project by adding the following element to your .csproj file, for example, immediately following the `LangVersion` element that enabled C# 8.0:</span></span>

```xml
<NullableContextOptions>enable</NullableContextOptions>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="f7d67-140">Проектирование типов для приложения</span><span class="sxs-lookup"><span data-stu-id="f7d67-140">Design the types for the application</span></span>

<span data-ttu-id="f7d67-141">Для этого приложения опроса требуется создать ряд классов:</span><span class="sxs-lookup"><span data-stu-id="f7d67-141">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="f7d67-142">Класс, моделирующий список вопросов.</span><span class="sxs-lookup"><span data-stu-id="f7d67-142">A class that models the list of questions.</span></span>
- <span data-ttu-id="f7d67-143">Класс, моделирующий список людей, с которыми связались для опроса.</span><span class="sxs-lookup"><span data-stu-id="f7d67-143">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="f7d67-144">Класс, моделирующий ответы человека, принявшего участие в опросе.</span><span class="sxs-lookup"><span data-stu-id="f7d67-144">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="f7d67-145">Эти типы будут использовать ссылочные типы, допускающие значения null и не допускающие значения null, чтобы выразить, какие элементы являются обязательными, а какие — необязательными.</span><span class="sxs-lookup"><span data-stu-id="f7d67-145">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="f7d67-146">Ссылочные типы, допускающие значение null, четко указывают на это намерение проекта:</span><span class="sxs-lookup"><span data-stu-id="f7d67-146">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="f7d67-147">Вопросы, входящие в опрос, не могут иметь значение null: Нет смысла задавать пустой вопрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-147">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="f7d67-148">Респонденты никогда не могут принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-148">The respondents can never be null.</span></span> <span data-ttu-id="f7d67-149">Следует отслеживать людей, с которыми вы связались, включая респондентов, которые отказались участвовать.</span><span class="sxs-lookup"><span data-stu-id="f7d67-149">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="f7d67-150">Любой ответ на вопрос может принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-150">Any response to a question may be null.</span></span> <span data-ttu-id="f7d67-151">Респонденты могут отказаться отвечать на некоторые или все вопросы.</span><span class="sxs-lookup"><span data-stu-id="f7d67-151">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="f7d67-152">Если вы программировали на C#, возможно, вы так привыкли ссылаться на типы, допускающие значение null, что упустили другие возможности для объявления экземпляров, не допускающих значение null:</span><span class="sxs-lookup"><span data-stu-id="f7d67-152">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="f7d67-153">Набор вопросов не должен допускать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-153">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="f7d67-154">Набор ответов не должен допускать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-154">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="f7d67-155">При написании кода вы увидите, что если ссылочный тип, не допускающий значение null, является типом по умолчанию для ссылок, это позволяет избежать распространенных ошибок, которые могут привести к исключениям из-за пустых ссылок.</span><span class="sxs-lookup"><span data-stu-id="f7d67-155">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="f7d67-156">В этом руководстве описана важность принятия решений о том, какие переменные могут или не могут принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-156">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="f7d67-157">Язык не предоставлял синтаксис для выражения этих решений,</span><span class="sxs-lookup"><span data-stu-id="f7d67-157">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="f7d67-158">а теперь предоставляет.</span><span class="sxs-lookup"><span data-stu-id="f7d67-158">Now it does.</span></span>

<span data-ttu-id="f7d67-159">Приложение, которое вы создадите, будет выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f7d67-159">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="f7d67-160">Создание опроса и добавление в него вопросов.</span><span class="sxs-lookup"><span data-stu-id="f7d67-160">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="f7d67-161">Создание псевдослучайного набора респондентов для опроса.</span><span class="sxs-lookup"><span data-stu-id="f7d67-161">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="f7d67-162">Связь с респондентами, пока размер опроса не достигает целевого значения.</span><span class="sxs-lookup"><span data-stu-id="f7d67-162">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="f7d67-163">Запись важных статистических данных на основе ответов на опрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-163">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="f7d67-164">Создание опроса с типами, допускающими и не допускающими значение null</span><span class="sxs-lookup"><span data-stu-id="f7d67-164">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="f7d67-165">Первый код, который вы напишете, создает опрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-165">The first code you'll write creates the survey.</span></span> <span data-ttu-id="f7d67-166">Вы напишете классы для моделирования вопроса и выполнения опроса.</span><span class="sxs-lookup"><span data-stu-id="f7d67-166">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="f7d67-167">Опрос состоит из вопросов трех типов, различающихся форматом ответов: да или нет, числовые ответы и текстовые ответы.</span><span class="sxs-lookup"><span data-stu-id="f7d67-167">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="f7d67-168">Создайте класс `public` `SurveyQuestion`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-168">Create a `public` `SurveyQuestion` class.</span></span> <span data-ttu-id="f7d67-169">Включите директиву pragma `#nullable enable` сразу после инструкций `using`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-169">Include the `#nullable enable` pragma immediately after the `using` statements:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="f7d67-170">Добавление директивы pragma `#nullable enable` означает, что компилятор интерпретирует каждое объявление переменной ссылочного типа как ссылочный тип **, не допускающий значение null**.</span><span class="sxs-lookup"><span data-stu-id="f7d67-170">Adding the `#nullable enable` pragma means the compiler interprets every reference type variable declaration as a **non-nullable** reference type.</span></span> <span data-ttu-id="f7d67-171">Первое предупреждение вы увидите после добавления свойств текста и типа вопроса, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f7d67-171">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="f7d67-172">Так как вы еще не инициализировали `QuestionText`, компилятор выдает предупреждение о том, что свойство, не допускающее значение null, не инициализировано.</span><span class="sxs-lookup"><span data-stu-id="f7d67-172">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="f7d67-173">Для проекта требуется, чтобы текст вопроса не принимал значение null, поэтому необходимо добавить конструктор, чтобы инициализировать свойство и значение `QuestionType`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-173">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="f7d67-174">Законченное определение класса выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f7d67-174">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="f7d67-175">После добавления конструктора предупреждение удаляется.</span><span class="sxs-lookup"><span data-stu-id="f7d67-175">Adding the constructor removes the warning.</span></span> <span data-ttu-id="f7d67-176">Аргумент конструктора также является ссылочным типом, не допускающим значение null, поэтому компилятор не выдает никаких предупреждений.</span><span class="sxs-lookup"><span data-stu-id="f7d67-176">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="f7d67-177">Затем создайте класс `public` с именем `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-177">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="f7d67-178">Включите директиву pragma `#nullable enable` после инструкций `using`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-178">Include the `#nullable enable` pragma following the `using` statements.</span></span> <span data-ttu-id="f7d67-179">Этот класс содержит список объектов `SurveyQuestion` и методов для добавления вопросов в опрос, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f7d67-179">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

#nullable enable
namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="f7d67-180">Как и раньше, необходимо инициализировать объект списка с помощью значения, отличного от null, или компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="f7d67-180">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="f7d67-181">При второй перегрузке `AddQuestion` не будет проверок значений null, так как они не требуются: вы объявили, что переменная не допускает значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-181">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="f7d67-182">Это значение не может быть равно `null`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-182">Its value can't be `null`.</span></span>

<span data-ttu-id="f7d67-183">Переключитесь на `Program.cs` в редакторе и замените содержимое метода `Main` следующими строками кода:</span><span class="sxs-lookup"><span data-stu-id="f7d67-183">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="f7d67-184">Так как в верхней части файла нет директивы pragma `#nullable enable`, компилятор не выдает предупреждение при передаче значения `null` в качестве текста аргумента `AddQuestion`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-184">Without the `#nullable enable` pragma at the top of the file, the compiler doesn't issue a warning when you pass `null` as the text for the `AddQuestion` argument.</span></span> <span data-ttu-id="f7d67-185">Исправить это можно, добавив `#nullable enable` после инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-185">Fix that by adding `#nullable enable` following the `using` statement.</span></span> <span data-ttu-id="f7d67-186">Попробуйте добавить следующую строку в `Main`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-186">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="f7d67-187">Создание респондентов и получение ответов на опрос</span><span class="sxs-lookup"><span data-stu-id="f7d67-187">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="f7d67-188">Теперь напишите код, который генерирует ответы на опрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-188">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="f7d67-189">Это включает в себя несколько мелких задач:</span><span class="sxs-lookup"><span data-stu-id="f7d67-189">This involves several small tasks:</span></span>

1. <span data-ttu-id="f7d67-190">Создать метод, генерирующий объекты-респонденты.</span><span class="sxs-lookup"><span data-stu-id="f7d67-190">Build a method that generates respondent objects.</span></span> <span data-ttu-id="f7d67-191">Они представляют людей, которых просят пройти опрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-191">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="f7d67-192">Создать логику, чтобы имитировать процесс задания вопросов респонденту и собирать ответы или отмечать, что респондент не ответил.</span><span class="sxs-lookup"><span data-stu-id="f7d67-192">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="f7d67-193">Повторять опрос до тех пор, пока нужное количество респондентов не ответит на вопросы.</span><span class="sxs-lookup"><span data-stu-id="f7d67-193">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="f7d67-194">Вам понадобится класс для представления ответа на опрос, поэтому добавьте его сейчас.</span><span class="sxs-lookup"><span data-stu-id="f7d67-194">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="f7d67-195">Включите поддержку значений null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-195">Enable nullable support.</span></span> <span data-ttu-id="f7d67-196">Добавьте свойство `Id` и конструктор, который его инициализирует, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f7d67-196">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="f7d67-197">Затем добавьте метод `static` для создания новых участников путем генерации случайного идентификатора:</span><span class="sxs-lookup"><span data-stu-id="f7d67-197">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="f7d67-198">Основная задача этого класса состоит в том, чтобы генерировать ответы участников на вопросы в опросе.</span><span class="sxs-lookup"><span data-stu-id="f7d67-198">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="f7d67-199">Эта задача состоит из нескольких шагов:</span><span class="sxs-lookup"><span data-stu-id="f7d67-199">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="f7d67-200">Запросите участие в опросе.</span><span class="sxs-lookup"><span data-stu-id="f7d67-200">Ask for participation in the survey.</span></span> <span data-ttu-id="f7d67-201">Если пользователь не согласен, верните отсутствующий (или null) ответ.</span><span class="sxs-lookup"><span data-stu-id="f7d67-201">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="f7d67-202">Задайте каждый вопрос и запишите ответы.</span><span class="sxs-lookup"><span data-stu-id="f7d67-202">Ask each question and record the answer.</span></span> <span data-ttu-id="f7d67-203">Любой ответ может отсутствовать (или иметь значение null).</span><span class="sxs-lookup"><span data-stu-id="f7d67-203">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="f7d67-204">Добавьте приведенный ниже код к классу `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-204">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="f7d67-205">Хранилищем для ответов на опрос является `Dictionary<int, string>?`, из которого видно, что оно может принимать значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-205">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="f7d67-206">Используйте новую языковую функцию, чтобы объявить намерение проекта как компилятору, так и всем, кто будет работать с кодом позже.</span><span class="sxs-lookup"><span data-stu-id="f7d67-206">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="f7d67-207">Если вы когда-нибудь разыменуете `surveyResponses`, не проверив значения null, компилятор отобразит предупреждение.</span><span class="sxs-lookup"><span data-stu-id="f7d67-207">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="f7d67-208">В методе `AnswerSurvey` предупреждение не отображается, так как компилятор может определить, что переменной `surveyResponses` ранее было присвоено значение, отличное от null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-208">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="f7d67-209">Далее необходимо написать метод `PerformSurvey` в классе `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-209">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="f7d67-210">Добавьте в класс `SurveyRun` следующий код:</span><span class="sxs-lookup"><span data-stu-id="f7d67-210">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="f7d67-211">В этом случае выбор `List<SurveyResponse>?` с возможностью принимать значение null указывает на то, что ответ может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="f7d67-211">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="f7d67-212">Это значит, что респонденты еще не участвовали в опросе.</span><span class="sxs-lookup"><span data-stu-id="f7d67-212">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="f7d67-213">Обратите внимание, что респонденты добавляются до тех пор, пока не будет достигнуто целевое значение.</span><span class="sxs-lookup"><span data-stu-id="f7d67-213">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="f7d67-214">Для запуска опроса осталось добавить вызов в конце метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-214">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="f7d67-215">Анализ ответов на опросы</span><span class="sxs-lookup"><span data-stu-id="f7d67-215">Examine survey responses</span></span>

<span data-ttu-id="f7d67-216">Далее следует отобразить ответы на опрос.</span><span class="sxs-lookup"><span data-stu-id="f7d67-216">The last step is to display survey results.</span></span> <span data-ttu-id="f7d67-217">Добавьте код во многие из написанных вами классов.</span><span class="sxs-lookup"><span data-stu-id="f7d67-217">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="f7d67-218">Этот код демонстрирует различие ссылочных типов, допускающих и не допускающих значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-218">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="f7d67-219">Начните с добавления элементов, воплощающих выражение, в класс `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-219">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="f7d67-220">Так как `surveyResponses` является ссылочным типом, не допускающим значение null, прежде чем отменять ссылку на него, укажите, что проверка не требуется.</span><span class="sxs-lookup"><span data-stu-id="f7d67-220">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="f7d67-221">Метод `Answer` возвращает строку, не допускающую значение null, поэтому выберите перегрузку `GetValueOrDefault`, которая принимает второй аргумент как значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f7d67-221">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="f7d67-222">Затем добавьте эти три элемента, воплощающие выражение, в класс `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-222">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="f7d67-223">Элемент `AllParticipants` должен принимать во внимание, что переменная `respondents` может иметь значение null, но возвращаемое значение не может быть равно null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-223">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="f7d67-224">Если изменить это выражение, удалив `??` и следующую пустую последовательность, компилятор выдаст предупреждение о том, что метод может возвращать `null`, а его сигнатура возвращает тип, не допускающий значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-224">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="f7d67-225">Наконец, добавьте следующий цикл в нижней части метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="f7d67-225">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="f7d67-226">В этом коде не требуется никаких проверок `null`, так как вы разработали базовые интерфейсы так, чтобы они возвращали ссылочные типы, не допускающие значения null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-226">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="f7d67-227">Получение кода</span><span class="sxs-lookup"><span data-stu-id="f7d67-227">Get the code</span></span>

<span data-ttu-id="f7d67-228">Вы можете получить код этого руководства из нашего репозитория [samples](https://github.com/dotnet/samples) в папке [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).</span><span class="sxs-lookup"><span data-stu-id="f7d67-228">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="f7d67-229">Экспериментируйте, изменяя объявления типов между ссылочными типами, допускающими и не допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-229">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="f7d67-230">Посмотрите, как создаются различные предупреждения, чтобы избежать случайного разыменования `null`.</span><span class="sxs-lookup"><span data-stu-id="f7d67-230">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7d67-231">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f7d67-231">Next steps</span></span>

<span data-ttu-id="f7d67-232">Дополнительные сведения см. в обзоре ссылочных типов, допускающих значение null.</span><span class="sxs-lookup"><span data-stu-id="f7d67-232">Learn more by reading an overview of nullable reference types..</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f7d67-233">Обзор ссылочных типов, допускающих значение null</span><span class="sxs-lookup"><span data-stu-id="f7d67-233">An overview of nullable references</span></span>](../nullable-references.md)
