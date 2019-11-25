---
title: Выражения C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: d1728758a4f1af76c2d08695a83c0f9acc3dde3e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140094"
---
# <a name="c-expressions"></a><span data-ttu-id="928c3-102">Выражения C#</span><span class="sxs-lookup"><span data-stu-id="928c3-102">C# Expressions</span></span>
<span data-ttu-id="928c3-103">Начиная с .NET Framework 4,5, C# выражения поддерживаются в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="928c3-103">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="928c3-104">Новые C# проекты рабочих процессов, созданные в Visual Studio 2012, предназначенные C# для .NET Framework 4,5, используют выражения, а проекты рабочих процессов Visual Basic используют выражения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="928c3-104">New C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="928c3-105">Существующие проекты рабочих процессов .NET Framework 4, использующие выражения Visual Basic, можно перенести в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] независимо от языка проекта и поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="928c3-105">Existing .NET Framework 4 workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="928c3-106">В этом разделе приведены общие сведения о выражениях на языке C# в [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="928c3-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="928c3-107">Выражения на языке C# в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="928c3-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="928c3-108">Использование C# выражений в конструктор рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="928c3-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

  - [<span data-ttu-id="928c3-109">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="928c3-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="928c3-110">Использование C# выражений в рабочих процессах кода</span><span class="sxs-lookup"><span data-stu-id="928c3-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="928c3-111">Использование C# выражений в рабочих ПРОЦЕССах XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

  - [<span data-ttu-id="928c3-112">Скомпилированный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

  - [<span data-ttu-id="928c3-113">Свободный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="928c3-114">Использование C# выражений в службах рабочих процессов XAMLX</span><span class="sxs-lookup"><span data-stu-id="928c3-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a><span data-ttu-id="928c3-115">Использование C# выражений в конструктор рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="928c3-115">Using C# expressions in the Workflow Designer</span></span>

<span data-ttu-id="928c3-116">Начиная с .NET Framework 4,5, C# выражения поддерживаются в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="928c3-116">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="928c3-117">C#проекты рабочих процессов, созданные в Visual Studio 2012, предназначенные C# для .NET Framework 4,5, используют выражения, тогда как Visual Basic проекты рабочих процессов используют выражения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="928c3-117">C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="928c3-118">Чтобы указать нужное C# выражение, введите его в поле с надписью **введите C# выражение**.</span><span class="sxs-lookup"><span data-stu-id="928c3-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="928c3-119">Эта метка отображается в окне свойств при выборе действия в конструкторе или при работе в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="928c3-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="928c3-120">В следующем примере два действия `WriteLine` содержатся в `Sequence` внутри `NoPersistScope`.</span><span class="sxs-lookup"><span data-stu-id="928c3-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

![Снимок экрана, на котором показано автоматически созданное действие последовательности.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> <span data-ttu-id="928c3-122">C#выражения поддерживаются только в Visual Studio и не поддерживаются в конструкторе рабочих процессов, размещенном повторно.</span><span class="sxs-lookup"><span data-stu-id="928c3-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="928c3-123">Дополнительные сведения о новых функциях WF45, поддерживаемых в повторно размещенном конструкторе, см. в разделе [Поддержка новых функций Workflow Foundation 4,5 в](wf-features-in-the-rehosted-workflow-designer.md)переразмещенной конструктор рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="928c3-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="BackwardCompat"></a><span data-ttu-id="928c3-124">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="928c3-124">Backwards compatibility</span></span>

<span data-ttu-id="928c3-125">Поддерживаются Visual Basic выражения в существующих C# проектах рабочих процессов .NET Framework 4, которые были перенесены в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="928c3-125">Visual Basic expressions in existing .NET Framework 4 C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="928c3-126">Когда Visual Basic выражения просматриваются в конструкторе рабочих процессов, текст существующего выражения Visual Basic заменяется значением, **установленным в XAML**, если только выражение Visual Basic не является допустимым C# синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="928c3-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="928c3-127">Если выражение Visual Basic имеет допустимый синтаксис C#, то отображается выражение.</span><span class="sxs-lookup"><span data-stu-id="928c3-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="928c3-128">Чтобы обновить выражение Visual Basic до C#, следует отредактировать его в конструкторе рабочих процессов и указать эквивалентное выражение C#.</span><span class="sxs-lookup"><span data-stu-id="928c3-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="928c3-129">Преобразование выражений Visual Basic в C# не является обязательным, но после обновления выражений в конструкторе рабочих процессов они преобразуется в C# и не могут быть восстановлены в виде выражений Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="928c3-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="CodeWorkflows"></a><span data-ttu-id="928c3-130">Использование C# выражений в рабочих процессах кода</span><span class="sxs-lookup"><span data-stu-id="928c3-130">Using C# expressions in code workflows</span></span>

<span data-ttu-id="928c3-131">Выражения на языке C# поддерживаются в рабочих процессах [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] с кодом, но до того, как рабочий процесс может быть вызван, выражения C# необходимо скомпилировать с помощью <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="928c3-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="928c3-132">Авторы рабочих процессов могут использовать `CSharpValue` для представления r-значений выражения и `CSharpReference` для представления l-значений выражения.</span><span class="sxs-lookup"><span data-stu-id="928c3-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="928c3-133">В следующем примере рабочий процесс создается с помощью действия `Assign` и действия `WriteLine`, содержащихся в `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="928c3-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="928c3-134">`CSharpReference` указывается для аргумента `To` действия `Assign` и представляет l-значение выражения.</span><span class="sxs-lookup"><span data-stu-id="928c3-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="928c3-135">`CSharpValue` указывается для аргумента `Value` действия `Assign` и для аргумента `Text` действия `WriteLine` и представляет r-значение для двух этих выражений.</span><span class="sxs-lookup"><span data-stu-id="928c3-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

<span data-ttu-id="928c3-136">После создания рабочего процесса выражения на языке C# компилируются с помощью вызова вспомогательного метода `CompileExpressions`, а затем уже вызывается рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="928c3-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="928c3-137">В следующем примере приведен метод `CompileExpressions`.</span><span class="sxs-lookup"><span data-stu-id="928c3-137">The following example is the `CompileExpressions` method.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
> <span data-ttu-id="928c3-138">Если C# выражения не компилируются, выдается <xref:System.NotSupportedException> при вызове рабочего процесса с сообщением следующего вида: `Expression Activity type 'CSharpValue`1 "требует компиляции для выполнения.</span><span class="sxs-lookup"><span data-stu-id="928c3-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="928c3-139">Убедитесь, что рабочий процесс был скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="928c3-139">Please ensure that the workflow has been compiled.\`</span></span>

<span data-ttu-id="928c3-140">Если рабочий процесс на основе пользовательского кода использует `DynamicActivity`, то требуется внести некоторые изменения в методе `CompileExpressions`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="928c3-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

<span data-ttu-id="928c3-141">Существует несколько различий в перегрузке `CompileExpressions`, которая компилирует выражения C# в динамическом действии.</span><span class="sxs-lookup"><span data-stu-id="928c3-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="928c3-142">Параметр в `CompileExpressions` - это `DynamicActivity`.</span><span class="sxs-lookup"><span data-stu-id="928c3-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="928c3-143">Имя типа и пространство имен получаются с помощью свойства `DynamicActivity.Name`.</span><span class="sxs-lookup"><span data-stu-id="928c3-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="928c3-144">Параметру `TextExpressionCompilerSettings.ForImplementation` задается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="928c3-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="928c3-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` вызывается вместо `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span><span class="sxs-lookup"><span data-stu-id="928c3-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

<span data-ttu-id="928c3-146">Дополнительные сведения о работе с выражениями в коде см. в разделе [создание рабочих процессов, действий и выражений с помощью императивного кода](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="XamlWorkflows"></a><span data-ttu-id="928c3-147">Использование C# выражений в рабочих ПРОЦЕССах XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-147">Using C# expressions in XAML workflows</span></span>

<span data-ttu-id="928c3-148">Выражения на языке C# поддерживаются в рабочих процессах языка XAML.</span><span class="sxs-lookup"><span data-stu-id="928c3-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="928c3-149">Скомпилированные рабочие процессы языка XAML компилируются в тип, свободные рабочие процессы языка XAML загружаются средой выполнения и компилируются в дерево действий при выполнении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="928c3-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="928c3-150">Скомпилированный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="928c3-151">Свободный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a><span data-ttu-id="928c3-152">Скомпилированный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-152">Compiled Xaml</span></span>

<span data-ttu-id="928c3-153">Выражения на языке C# поддерживаются в скомпилированных рабочих процессах языка XAML, которые компилируются в тип как часть проекта рабочего процесса C#, целью для которых является [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="928c3-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="928c3-154">Скомпилированный XAML является типом по умолчанию для создания рабочих процессов в Visual C# Studio, а проекты рабочих процессов, созданные в Visual C# studio, предназначены для [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] использования выражений.</span><span class="sxs-lookup"><span data-stu-id="928c3-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="LooseXaml"></a><span data-ttu-id="928c3-155">Свободный XAML</span><span class="sxs-lookup"><span data-stu-id="928c3-155">Loose Xaml</span></span>

<span data-ttu-id="928c3-156">Выражения на языке C# поддерживаются в свободных рабочих процессах языка XAML.</span><span class="sxs-lookup"><span data-stu-id="928c3-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="928c3-157">Программа размещения рабочего процесса, которая загружает и вызывает свободный рабочий процесс языка XAML, должна иметь целью компиляции [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] и <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> должно быть задано значение `true` (по умолчанию `false`).</span><span class="sxs-lookup"><span data-stu-id="928c3-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="928c3-158">Чтобы установить свойству <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> значение `true`, создайте экземпляр <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> со свойством <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>, установленным в значение `true`, и передайте его как параметр в <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="928c3-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="928c3-159">Если для `CompileExpressions` не задано значение `true`, будет создано исключение <xref:System.NotSupportedException> с сообщением следующего вида: `Expression Activity type 'CSharpValue`1 "требует компиляции для выполнения.</span><span class="sxs-lookup"><span data-stu-id="928c3-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="928c3-160">Убедитесь, что рабочий процесс был скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="928c3-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="928c3-161">Дополнительные сведения о работе с рабочими процессами XAML см. [в разделе Сериализация рабочих процессов и действий в XAML и обратно](serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="928c3-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="WFServices"></a><span data-ttu-id="928c3-162">Использование C# выражений в службах рабочих процессов XAMLX</span><span class="sxs-lookup"><span data-stu-id="928c3-162">Using C# expressions in XAMLX workflow services</span></span>

<span data-ttu-id="928c3-163">Выражения на языке C# поддерживаются в службах рабочих процессов XAMLX.</span><span class="sxs-lookup"><span data-stu-id="928c3-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="928c3-164">Если служба рабочего процесса размещается в IIS или WAS, то дополнительные действия не требуются. Но если служба рабочих процессов языка XAML является резидентной, то выражения C# необходимо скомпилировать.</span><span class="sxs-lookup"><span data-stu-id="928c3-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="928c3-165">Чтобы скомпилировать C# выражения в локальной службе рабочего процесса xamlx, сначала загрузите файл XAMLX в `WorkflowService`, а затем передайте `Body` `WorkflowService` методу `CompileExpressions`, описанному в разделе "предыдущие [выражения using C# в рабочих процессах кода](csharp-expressions.md#CodeWorkflows) ".</span><span class="sxs-lookup"><span data-stu-id="928c3-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="928c3-166">В следующем примере загружается служба рабочих процессов XAMLX, компилируются выражения на языке C#, затем открывается служба рабочих процессов, которая начинает ожидать запросы.</span><span class="sxs-lookup"><span data-stu-id="928c3-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

<span data-ttu-id="928c3-167">Если выражения C# не скомпилированы, операция `Open` выполняется успешно, но при вызове рабочий процесс завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="928c3-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="928c3-168">Следующий метод `CompileExpressions` тот же, что и метод из предыдущего раздела [использование C# выражений в рабочих процессах кода](csharp-expressions.md#CodeWorkflows) .</span><span class="sxs-lookup"><span data-stu-id="928c3-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
