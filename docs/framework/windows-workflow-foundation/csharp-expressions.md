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
# <a name="c-expressions"></a>Выражения C#
Начиная с .NET Framework 4,5, C# выражения поддерживаются в Windows Workflow Foundation (WF). Новые C# проекты рабочих процессов, созданные в Visual Studio 2012, предназначенные C# для .NET Framework 4,5, используют выражения, а проекты рабочих процессов Visual Basic используют выражения Visual Basic. Существующие проекты рабочих процессов .NET Framework 4, использующие выражения Visual Basic, можно перенести в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] независимо от языка проекта и поддерживаются. В этом разделе приведены общие сведения о выражениях на языке C# в [!INCLUDE[wf1](../../../includes/wf1-md.md)].

## <a name="using-c-expressions-in-workflows"></a>Выражения на языке C# в рабочих процессах

- [Использование C# выражений в конструктор рабочих процессов](csharp-expressions.md#WFDesigner)

  - [Обратная совместимость](csharp-expressions.md#BackwardCompat)

- [Использование C# выражений в рабочих процессах кода](csharp-expressions.md#CodeWorkflows)

- [Использование C# выражений в рабочих ПРОЦЕССах XAML](csharp-expressions.md#XamlWorkflows)

  - [Скомпилированный XAML](csharp-expressions.md#CompiledXaml)

  - [Свободный XAML](csharp-expressions.md#LooseXaml)

- [Использование C# выражений в службах рабочих процессов XAMLX](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a>Использование C# выражений в конструктор рабочих процессов

Начиная с .NET Framework 4,5, C# выражения поддерживаются в Windows Workflow Foundation (WF). C#проекты рабочих процессов, созданные в Visual Studio 2012, предназначенные C# для .NET Framework 4,5, используют выражения, тогда как Visual Basic проекты рабочих процессов используют выражения Visual Basic. Чтобы указать нужное C# выражение, введите его в поле с надписью **введите C# выражение**. Эта метка отображается в окне свойств при выборе действия в конструкторе или при работе в конструкторе рабочих процессов. В следующем примере два действия `WriteLine` содержатся в `Sequence` внутри `NoPersistScope`.

![Снимок экрана, на котором показано автоматически созданное действие последовательности.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> C#выражения поддерживаются только в Visual Studio и не поддерживаются в конструкторе рабочих процессов, размещенном повторно. Дополнительные сведения о новых функциях WF45, поддерживаемых в повторно размещенном конструкторе, см. в разделе [Поддержка новых функций Workflow Foundation 4,5 в](wf-features-in-the-rehosted-workflow-designer.md)переразмещенной конструктор рабочих процессов.

#### <a name="BackwardCompat"></a>Обратная совместимость

Поддерживаются Visual Basic выражения в существующих C# проектах рабочих процессов .NET Framework 4, которые были перенесены в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Когда Visual Basic выражения просматриваются в конструкторе рабочих процессов, текст существующего выражения Visual Basic заменяется значением, **установленным в XAML**, если только выражение Visual Basic не является допустимым C# синтаксисом. Если выражение Visual Basic имеет допустимый синтаксис C#, то отображается выражение. Чтобы обновить выражение Visual Basic до C#, следует отредактировать его в конструкторе рабочих процессов и указать эквивалентное выражение C#. Преобразование выражений Visual Basic в C# не является обязательным, но после обновления выражений в конструкторе рабочих процессов они преобразуется в C# и не могут быть восстановлены в виде выражений Visual Basic.

### <a name="CodeWorkflows"></a>Использование C# выражений в рабочих процессах кода

Выражения на языке C# поддерживаются в рабочих процессах [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] с кодом, но до того, как рабочий процесс может быть вызван, выражения C# необходимо скомпилировать с помощью <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>. Авторы рабочих процессов могут использовать `CSharpValue` для представления r-значений выражения и `CSharpReference` для представления l-значений выражения. В следующем примере рабочий процесс создается с помощью действия `Assign` и действия `WriteLine`, содержащихся в `Sequence`. `CSharpReference` указывается для аргумента `To` действия `Assign` и представляет l-значение выражения. `CSharpValue` указывается для аргумента `Value` действия `Assign` и для аргумента `Text` действия `WriteLine` и представляет r-значение для двух этих выражений.

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

После создания рабочего процесса выражения на языке C# компилируются с помощью вызова вспомогательного метода `CompileExpressions`, а затем уже вызывается рабочий процесс. В следующем примере приведен метод `CompileExpressions`.

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
> Если C# выражения не компилируются, выдается <xref:System.NotSupportedException> при вызове рабочего процесса с сообщением следующего вида: `Expression Activity type 'CSharpValue`1 "требует компиляции для выполнения.  Убедитесь, что рабочий процесс был скомпилирован.

Если рабочий процесс на основе пользовательского кода использует `DynamicActivity`, то требуется внести некоторые изменения в методе `CompileExpressions`, как показано в следующем примере кода.

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

Существует несколько различий в перегрузке `CompileExpressions`, которая компилирует выражения C# в динамическом действии.

- Параметр в `CompileExpressions` - это `DynamicActivity`.

- Имя типа и пространство имен получаются с помощью свойства `DynamicActivity.Name`.

- Параметру `TextExpressionCompilerSettings.ForImplementation` задается значение `true`.

- `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` вызывается вместо `CompiledExpressionInvoker.SetCompiledExpressionRoot`.

Дополнительные сведения о работе с выражениями в коде см. в разделе [создание рабочих процессов, действий и выражений с помощью императивного кода](authoring-workflows-activities-and-expressions-using-imperative-code.md).

### <a name="XamlWorkflows"></a>Использование C# выражений в рабочих ПРОЦЕССах XAML

Выражения на языке C# поддерживаются в рабочих процессах языка XAML. Скомпилированные рабочие процессы языка XAML компилируются в тип, свободные рабочие процессы языка XAML загружаются средой выполнения и компилируются в дерево действий при выполнении рабочего процесса.

- [Скомпилированный XAML](csharp-expressions.md#CompiledXaml)

- [Свободный XAML](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a>Скомпилированный XAML

Выражения на языке C# поддерживаются в скомпилированных рабочих процессах языка XAML, которые компилируются в тип как часть проекта рабочего процесса C#, целью для которых является [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Скомпилированный XAML является типом по умолчанию для создания рабочих процессов в Visual C# Studio, а проекты рабочих процессов, созданные в Visual C# studio, предназначены для [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] использования выражений.

#### <a name="LooseXaml"></a>Свободный XAML

Выражения на языке C# поддерживаются в свободных рабочих процессах языка XAML. Программа размещения рабочего процесса, которая загружает и вызывает свободный рабочий процесс языка XAML, должна иметь целью компиляции [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] и <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> должно быть задано значение `true` (по умолчанию `false`). Чтобы установить свойству <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> значение `true`, создайте экземпляр <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> со свойством <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>, установленным в значение `true`, и передайте его как параметр в <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>. Если для `CompileExpressions` не задано значение `true`, будет создано исключение <xref:System.NotSupportedException> с сообщением следующего вида: `Expression Activity type 'CSharpValue`1 "требует компиляции для выполнения.  Убедитесь, что рабочий процесс был скомпилирован.

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Дополнительные сведения о работе с рабочими процессами XAML см. [в разделе Сериализация рабочих процессов и действий в XAML и обратно](serializing-workflows-and-activities-to-and-from-xaml.md).

### <a name="WFServices"></a>Использование C# выражений в службах рабочих процессов XAMLX

Выражения на языке C# поддерживаются в службах рабочих процессов XAMLX. Если служба рабочего процесса размещается в IIS или WAS, то дополнительные действия не требуются. Но если служба рабочих процессов языка XAML является резидентной, то выражения C# необходимо скомпилировать. Чтобы скомпилировать C# выражения в локальной службе рабочего процесса xamlx, сначала загрузите файл XAMLX в `WorkflowService`, а затем передайте `Body` `WorkflowService` методу `CompileExpressions`, описанному в разделе "предыдущие [выражения using C# в рабочих процессах кода](csharp-expressions.md#CodeWorkflows) ". В следующем примере загружается служба рабочих процессов XAMLX, компилируются выражения на языке C#, затем открывается служба рабочих процессов, которая начинает ожидать запросы.

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

Если выражения C# не скомпилированы, операция `Open` выполняется успешно, но при вызове рабочий процесс завершится ошибкой. Следующий метод `CompileExpressions` тот же, что и метод из предыдущего раздела [использование C# выражений в рабочих процессах кода](csharp-expressions.md#CodeWorkflows) .

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
