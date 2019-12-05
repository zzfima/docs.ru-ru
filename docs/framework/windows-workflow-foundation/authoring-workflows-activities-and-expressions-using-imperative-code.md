---
title: Разработка рабочих процессов, действий и выражений с помощью императивного кода
ms.date: 03/30/2017
ms.assetid: cefc9cfc-2882-4eb9-8c94-7a6da957f2b2
ms.openlocfilehash: 97f57067e72be2ed2fb6b3846e2ab876c13e049f
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802704"
---
# <a name="authoring-workflows-activities-and-expressions-using-imperative-code"></a>Разработка рабочих процессов, действий и выражений с помощью императивного кода
Определение рабочего процесса представляет собой дерево настроенных объектов действий. Это дерево действий можно определить многими способами, включая редактирование XAML вручную и использование конструктора рабочих процессов для создания XAML. Но использование XAML не является обязательным. Определения рабочих процессов могут быть также созданы вручную. В этом разделе представлены общие сведения о создании определений, действий и выражений рабочего процесса с помощью кода. Примеры работы с рабочими процессами XAML с помощью кода см. [в разделе Сериализация рабочих процессов и действий в XAML и обратно](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
## <a name="creating-workflow-definitions"></a>Создание определений рабочих процессов  
 Определение рабочего процесса можно создать путем создания экземпляра типа действия и настройки свойств объекта действия. Для действий, которые не содержат дочерних действий, определение можно создать программно с помощью нескольких строк кода.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#47](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#47)]  
  
> [!NOTE]
> В примерах этого раздела для запуска рабочих процессов образцов используется <xref:System.Activities.WorkflowInvoker>. Дополнительные сведения о вызове рабочих процессов, передаче аргументов и различных доступных вариантах размещения см. в разделе [использование WorkflowInvoker и WorkflowApplication](using-workflowinvoker-and-workflowapplication.md).  
  
 В этом примере создается рабочий процесс, состоящий из одного действия <xref:System.Activities.Statements.WriteLine>. Задается аргумент <xref:System.Activities.Statements.WriteLine> действия <xref:System.Activities.Statements.WriteLine.Text%2A> и выполняется вызов рабочего процесса. Если в действии содержатся дочерние действия, то используется аналогичный метод построения. В следующем примере используется действие <xref:System.Activities.Statements.Sequence>, которое содержит два действия <xref:System.Activities.Statements.WriteLine>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#48](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#48)]  
  
### <a name="using-object-initializers"></a>Использование инициализаторов объектов  
 В примерах в этом разделе используется синтаксис инициализации объектов. Синтаксис инициализации объектов можно использовать для создания определений рабочих процессов в коде, поскольку он обеспечивает иерархическое представление действий в рабочем процессе и показывает связи между действиями. При программном создании рабочих процессов нет необходимости использовать синтаксис инициализации объектов. Следующий пример функционально эквивалентен предыдущему примеру.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#49](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#49)]  
  
 Дополнительные сведения об инициализаторах объектов см. [в разделе как инициализировать объекты без вызова конструктора (C# руководство по программированию)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) и [как объявить объект с помощью инициализатора объекта](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).  
  
### <a name="working-with-variables-literal-values-and-expressions"></a>Работа с переменными, литеральными значениями и выражениями  
 При создании определения рабочего процесса с помощью кода необходимо помнить, какая часть кода выполняется как часть создания определения рабочего процесса и какая часть кода выполняется как часть выполнения экземпляра рабочего процесса. Например, следующий рабочий процесс должен создавать случайное число и записывать его в консоль.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#50)]  
  
 После выполнения кода определения рабочего процесса происходит вызов `Random.Next` и результат сохраняется в определении рабочего процесса как литеральное значение. Можно вызвать несколько экземпляров этого рабочего процесса, при этом все они отобразят одно и то же число. Чтобы обеспечить создание случайного числа во время выполнения рабочего процесса, необходимо использовать выражение, которое вычисляется при каждом запуске рабочего процесса. В следующем примере выражение Visual Basic используется вместе с <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 Выражение из предыдущего примера также могло быть реализовано с помощью выражения <xref:Microsoft.CSharp.Activities.CSharpValue%601> и выражения C#.  
  
```csharp  
new Assign<int>  
{  
    To = n,  
    Value = new CSharpValue<int>("new Random().Next(1, 101)")  
}  
```  
  
 Выражения C# необходимо компилировать до того, как будет вызван рабочий процесс, содержащий их. Если выражения C# не компилируются, выдается метод <xref:System.NotSupportedException>, когда рабочий процесс вызывается с помощью сообщения следующего вида: ``Expression Activity type 'CSharpValue`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.`` В большинстве сценариев вызова рабочих процессов, созданных в Visual Studio, выражения C# компилируются автоматически, но в определенных случаях, например для рабочих процессов кода, выражения C# необходимо скомпилировать вручную. Пример компиляции C# выражений см. в разделе [ C# использование выражений в рабочих процессах кода](csharp-expressions.md#CodeWorkflows) в разделе [ C# выражения](csharp-expressions.md) .  
  
 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> представляет выражение в синтаксисе Visual Basic, которое может быть использовано в качестве правостороннего значения в выражении, а <xref:Microsoft.CSharp.Activities.CSharpValue%601> представляет выражение в синтаксисе Visual C#, которое может быть использовано в качестве правостороннего значения в выражении. Значения этих выражений вычисляются каждый раз при выполнении содержащего их действия. Результат выражения назначается переменной рабочего процесса `n`, и эти результаты используются следующим действием в рабочем процессе. Для получения доступа к значению переменной рабочего процесса `n` во время выполнения необходим контекст <xref:System.Activities.ActivityContext>. Доступ может быть получен с помощью следующего лямбда-выражения.  
  
> [!NOTE]
> Обратите внимание, что в обоих примерах используется код на языке C#, но в одном используется <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, а во втором - <xref:Microsoft.CSharp.Activities.CSharpValue%601>. <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> и <xref:Microsoft.CSharp.Activities.CSharpValue%601> могут использоваться в проектах Visual Basic и C#. По умолчанию выражения, созданные в конструкторе рабочих процессов, соответствуют языку проекта для размещения. При создании рабочих процессов в коде выбор языка остается за автором рабочего процесса.  
  
 В этих примерах результат выражения назначается переменной рабочего процесса `n` и эти результаты используются следующим действием в рабочем процессе. Для получения доступа к значению переменной рабочего процесса `n` во время выполнения необходим контекст <xref:System.Activities.ActivityContext>. Доступ может быть получен с помощью следующего лямбда-выражения.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#52](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#52)]  
  
 Дополнительные сведения о лямбда-выражениях см. в разделе [лямбда-выражения (C# руководством по программированию)](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) или [лямбда-выражения (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Лямбда-выражения не могут быть сериализованы в формат XAML. При попытке сериализовать рабочий процесс лямбда-выражениями возникает исключение <xref:System.Activities.Expressions.LambdaSerializationException> со следующим сообщением: «Этот рабочий процесс содержит указанные в коде лямбда-выражения. Эти выражения XAML-несериализуемы. Чтобы сделать рабочий процесс XAML-сериализуемым, используйте или VisualBasicValue/VisualBasicReference, или ExpressionServices.Convert(lambda). При этом лямбда-выражения будут преобразованы в действия выражений». Чтобы обеспечить совместимость этого выражения с XAML, используйте <xref:System.Activities.Expressions.ExpressionServices> и <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>, как показано в следующем примере.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#53](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#53)]  
  
 Можно также использовать <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>. Обратите внимание, что при использовании выражений Visual Basic можно обойтись без лямбда-выражений.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#54](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#54)]  
  
 Во время выполнения выражения Visual Basic компилируются в выражения LINQ. Оба приведенных примера сериализуются в языке XAML, однако, если сериализованный язык XAML должен просматриваться и изменяться в конструкторе рабочих процессов, используйте для выражений <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>. Сериализованные рабочие процессы, использующие `ExpressionServices.Convert`, могут быть открыты в конструкторе, но значение выражения будет пустым. Дополнительные сведения о сериализации рабочих процессов в XAML см. [в разделе Сериализация рабочих процессов и действий в XAML и обратно](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
#### <a name="literal-expressions-and-reference-types"></a>Литеральные выражения и ссылочные типы  
 Литеральные выражения представляются действием <xref:System.Activities.Expressions.Literal%601> в рабочем процессе. Следующие действия <xref:System.Activities.Statements.WriteLine> функционально эквивалентны.  
  
```csharp  
new WriteLine  
{  
    Text = "Hello World."  
},  
new WriteLine  
{  
    Text = new Literal<string>("Hello World.")  
}  
```  
  
 Недопустимо инициализировать литеральное выражение любым ссылочным типом, за исключением <xref:System.String>. В следующем примере свойство <xref:System.Activities.Statements.Assign> действия <xref:System.Activities.Statements.Assign.Value%2A> инициализируется литеральным выражением с помощью `List<string>`.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new List<string>())  
},  
```  
  
 Когда рабочий процесс, содержащий это действие, проверяется, возникает следующая ошибка проверки: «Литералы поддерживают лишь типы значений и неизменяемый тип System.String. Тип System.Collections.Generic.List`1[System.String] нельзя использовать в качестве литерала». Если вызывается рабочий процесс, появляется уведомление <xref:System.Activities.InvalidWorkflowException>, содержащее сообщение об ошибке проверки. Это ошибка проверки, поскольку при создании литерального выражения со ссылочным типом не создается новый экземпляр ссылочного типа для каждого из экземпляров рабочего процесса. Чтобы устранить эту проблему, замените литеральное выражение таким, которое создает и возвращает новый экземпляр ссылочного типа.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new VisualBasicValue<List<string>>("New List(Of String)"))  
},  
```  
  
 Дополнительные сведения о выражениях см. в разделе [выражения](expressions.md).  
  
#### <a name="invoking-methods-on-objects-using-expressions-and-the-invokemethod-activity"></a>Вызов методов в объектах с помощью выражений и действия InvokeMethod  
 Действие <xref:System.Activities.Expressions.InvokeMethod%601> можно использовать для вызова статических методов и методов экземпляров классов в платформе .NET Framework. В предыдущем примере этого раздела случайное число было создано с помощью класса <xref:System.Random>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 Действие <xref:System.Activities.Expressions.InvokeMethod%601> может также использоваться для вызова метода <xref:System.Random.Next%2A> класса <xref:System.Random>.  
  
```csharp  
new InvokeMethod<int>  
{  
    TargetObject = new InArgument<Random>(new VisualBasicValue<Random>("New Random()")),  
    MethodName = "Next",  
    Parameters =   
    {  
        new InArgument<int>(1),  
        new InArgument<int>(101)  
    },  
    Result = n  
}  
```  
  
 Поскольку <xref:System.Random.Next%2A> не статический метод, предоставляется экземпляр класса <xref:System.Random> для свойства <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A>. В этом примере создается новый экземпляр класса с использованием выражения Visual Basic, но он мог быть также создан ранее и сохранен в переменной рабочего процесса. В этом примере будет проще использовать действие <xref:System.Activities.Statements.Assign%601> вместо действия <xref:System.Activities.Expressions.InvokeMethod%601>. Если вызов метода, в конечном счете осуществляемый действием <xref:System.Activities.Statements.Assign%601> или действием <xref:System.Activities.Expressions.InvokeMethod%601>, является долго выполняющимся, преимущество имеет <xref:System.Activities.Expressions.InvokeMethod%601> за счет наличия свойства <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A>. Если это свойство имеет значение `true`, вызванный метод работает асинхронно относительно рабочего процесса. Если параллельно работают другие действия, они не будут заблокированы, пока метод выполняется асинхронно. Кроме того, если вызываемый метод не имеет возвращаемого значения, то для его вызова подойдет <xref:System.Activities.Expressions.InvokeMethod%601>.  
  
## <a name="arguments-and-dynamic-activities"></a>Аргументы и динамические действия  
 Определение рабочего процесса создается в коде путем сборки действий в дерево действий и настройки всех свойств и аргументов. Для существующих аргументов можно выполнить привязку, но новые аргументы нельзя добавить к действиям. Сюда относятся аргументы рабочего процесса, передаваемые корневому действию. В императивном коде аргументы рабочего процесса указываются как свойства для нового CLR-типа, а в XAML они объявляются с помощью `x:Class` и `x:Member`. Поскольку при создании определения рабочего процесса как дерева объектов, содержащихся в памяти, не создается нового CLR-типа, аргументы не могут быть добавлены. Однако аргументы могут быть добавлены к <xref:System.Activities.DynamicActivity>. В этом примере создается действие <xref:System.Activities.DynamicActivity%601>, которое принимает и складывает два целочисленных аргумента и возвращает результат. Для каждого аргумента создается свойство <xref:System.Activities.DynamicActivityProperty>, результат операции присваивается аргументу <xref:System.Activities.Activity%601.Result%2A> действия <xref:System.Activities.DynamicActivity%601>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#55](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#55)]  
  
 Дополнительные сведения о динамических действиях см. [в разделе Создание действия во время выполнения](creating-an-activity-at-runtime-with-dynamicactivity.md).  
  
## <a name="compiled-activities"></a>Скомпилированные действия  
 Динамические действия - это один из способов определить действие, которое содержит аргументы в коде, но действия также можно создавать в коде и компилировать в типы. Можно создавать простые действия, производные от класса <xref:System.Activities.CodeActivity>, и асинхронные действия, производные от класса <xref:System.Activities.AsyncCodeActivity>. Эти действия могут иметь аргументы и возвращаемые значения и задают логику с помощью императивного кода. Примеры создания таких типов действий см. в статьях [базовый класс CodeActivity](workflow-activity-authoring-using-the-codeactivity-class.md) и [Создание асинхронных действий](creating-asynchronous-activities-in-wf.md).  
  
 Действия, производные от <xref:System.Activities.NativeActivity>, могут определять свою логику с помощью императивного кода и содержать дочерние действия, определяющие логику. Кроме того, они имеют полный доступ к возможностям среды выполнения, таким как создание закладок. Примеры создания действия на основе <xref:System.Activities.NativeActivity>см. в разделе [базовый класс NativeActivity](nativeactivity-base-class.md), [инструкции: Создание действия](how-to-create-an-activity.md)и пример [пользовательской составной модели с использованием собственного действия](./samples/custom-composite-using-native-activity.md) .  
  
 Действия, производные от <xref:System.Activities.Activity>, задают логику исключительно с помощью дочерних действий. Эти действия обычно создаются с помощью конструктора рабочих процессов, а также могут быть заданы с помощью кода. В следующем примере определяется действие `Square`, являющееся производным от `Activity<int>`. Действие `Square` содержит класс <xref:System.Activities.InArgument%601> с именем `Value` и задает его логику, указав действие <xref:System.Activities.Statements.Sequence> с помощью свойства <xref:System.Activities.Activity.Implementation%2A>. Действие <xref:System.Activities.Statements.Sequence> содержит действие <xref:System.Activities.Statements.WriteLine> и действие <xref:System.Activities.Statements.Assign%601>. Совместно эти три действия реализуют логику действия `Square`.  
  
```csharp  
class Square : Activity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Value { get; set; }  
  
    public Square()  
    {  
        this.Implementation = () => new Sequence  
        {  
            Activities =  
            {  
                new WriteLine  
                {  
                    Text = new InArgument<string>((env) => "Squaring the value: " + this.Value.Get(env))  
                },  
                new Assign<int>  
                {  
                    To = new OutArgument<int>((env) => this.Result.Get(env)),  
                    Value = new InArgument<int>((env) => this.Value.Get(env) * this.Value.Get(env))  
                }  
            }  
        };  
    }  
}  
```  
  
 В следующем примере вызывается определение рабочего процесса, состоящего из одного действия `Square`, с помощью метода <xref:System.Activities.WorkflowInvoker>.  
  
```csharp  
Dictionary<string, object> inputs = new Dictionary<string, object> {{ "Value", 5}};  
int result = WorkflowInvoker.Invoke(new Square(), inputs);  
Console.WriteLine("Result: {0}", result);  
```  
  
 При вызове рабочего процесса на консоль выводятся следующие данные:  
  
 **Возведение в возведение значения: 5**  
**Результат: 25**
