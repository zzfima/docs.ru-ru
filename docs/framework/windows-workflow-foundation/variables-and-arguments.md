---
title: "Переменные и аргументы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Переменные и аргументы
В [!INCLUDE[wf](../../../includes/wf-md.md)] переменные представляют хранилище данных, а аргументы, представляют поток данных в действие и из действия.Действие имеет набор аргументов, которые составляют сигнатуру действия.Действие может также поддерживать список переменных, к которым разработчик может добавлять или удалять переменные при разработке рабочего процесса.Привязка аргумента выполнена с помощью выражения, возвращающего значение.  
  
## Переменные  
 Переменные представляют собой место хранения данных.Переменные объявляются в составе определения рабочего процесса.Переменные принимают значения во время выполнения, и эти значения сохраняются как часть состояния экземпляра рабочего процесса.Определение переменной указывает тип переменной и, возможно, имя.В следующем коде показано, как объявить переменную, присвоить ей значение с помощью действия <xref:System.Activities.Statements.Assign%601>, а затем отобразить ее значение на консоли с помощью действия <xref:System.Activities.Statements.WriteLine>.  
  
```csharp  
// Define a variable named "str" of type string.  
Variable<string> var = new Variable<string>  
{  
    Name = "str"  
};  
  
// Declare the variable within a Sequence, assign  
// a value to it, and then display it.  
Activity wf = new Sequence()  
{  
    Variables = { var },  
    Activities =  
    {  
        new Assign<string>  
        {  
            To = var,  
            Value = "Hello World."  
        },  
        new WriteLine  
        {  
            Text = var  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 Выражение значения по умолчанию может быть дополнительно указано как часть объявления переменной.У переменных также имеются модификаторы.Например, если переменная доступна только для чтения, то можно применить модификатор, доступный только для чтения <xref:System.Activities.VariableModifiers>.В следующем примере создается доступная только для чтения переменная, для которой задано значение по умолчанию.  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## Определение областей переменных  
 Время существования переменной во время выполнения равно времени существования действия, которое объявило эту переменную.После завершения действия выполняется очистка его переменных, после чего нельзя больше ссылаться на эти переменные.  
  
## Аргументы  
 Создатели действия используют аргументы для определения способов перемещения данных в действие и из действия.Все аргументы имеют указанные направления: <xref:System.Activities.ArgumentDirection>, <xref:System.Activities.ArgumentDirection> или <xref:System.Activities.ArgumentDirection>.  
  
 Среда выполнения рабочих процессов обеспечивает выполнение следующих условий, касающихся времени перемещения данных в действия и из действий:  
  
1.  После начала выполнения действия рассчитываются значения всех входных и входных\/выходных аргументов.Например, независимо от времени вызова <xref:System.Activities.Argument.Get%2A> возвращается значение, которое рассчитывается средой выполнения до его вызова `Execute`.  
  
2.  При вызове <xref:System.Activities.InOutArgument%601.Set%2A> среда выполнения немедленно задает значение.  
  
3.  Для аргументов может быть дополнительно задан их <xref:System.Activities.Argument.EvaluationOrder%2A>.<xref:System.Activities.Argument.EvaluationOrder%2A> — отсчитываемое от нуля значение, которое указывает порядок для вычисления аргумента.По умолчанию порядок вычисления аргумента не указан и равен значению <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>.Свойству <xref:System.Activities.Argument.EvaluationOrder%2A> задайте значение, большее или равное нулю, чтобы указать порядок вычисления для этого аргумента.[!INCLUDE[wf2](../../../includes/wf2-md.md)] вычисляет аргументы в заданном порядке вычисления, в убывающем порядке.Следует отметить, что аргументы с незаданным порядком вычисления вычисляются до вычисления аргументов, порядок вычисления которых задан.  
  
 Создатель действия для предоставления доступа к аргументам действия может использовать механизм со строгой типизацией.Для этого объявляются свойства типа <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> и <xref:System.Activities.InOutArgument%601>.Благодаря этому для создателя действия обеспечивается возможность установки определенного контракта, касающегося потока данных в действие и из действия.  
  
### Определение аргументов для действия  
 Для действия можно определить аргументы путем указания свойств типа <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> и <xref:System.Activities.InOutArgument%601>.В следующем коде показано определение аргументов для действия `Prompt`, принимающего строку для отображения для пользователя и возвращающего строку, которая содержит ответ пользователя.  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
>  Действия, которые возвращают одно значение, могут быть производными от <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> или <xref:System.Activities.CodeActivity%601>.У этих действий существует полностью определенный аргумент <xref:System.Activities.OutArgument%601> с именем <xref:System.Activities.Activity%601.Result%2A>, который содержит возвращаемое значение действия.  
  
### Использование переменных и аргументов в рабочих процессах  
 В следующем примере показано, как переменные и аргументы используются в рабочих процессах.Рабочий процесс представляет собой последовательность, объявляющую три переменные: `var1`, `var2` и `var3`.Первым действием в рабочем процессе является действие `Assign`, которое присваивает значение переменной `var1` переменной `var2`.За этим следует действие `WriteLine`, выполняющее печать значения переменной `var2`.Затем следует еще одно действие `Assign`, которое присваивает значение переменной `var2` переменной `var3`.И, наконец, существует еще одно действие `WriteLine`, выполняющее печать значения переменной `var3`.Первое действие `Assign` использует объекты и `InArgument<string>` и `OutArgument<string>`, которые явно представляют привязки аргументов действия.`InArgument<string>` используется для <xref:System.Activities.Statements.Assign.Value%2A>, поскольку значение передается действию <xref:System.Activities.Statements.Assign%601> с помощью его аргумента <xref:System.Activities.Statements.Assign.Value%2A>, а `OutArgument<string>` используется для <xref:System.Activities.Statements.Assign.To%2A>, поскольку значение передается от аргумента <xref:System.Activities.Statements.Assign.To%2A> переменной.Второе действие `Assign` позволяет добиться такого же результата с использованием более компактного, но аналогичного синтаксиса, в котором используются явные операции приведения.Действия `WriteLine` также используют компактный синтаксис.  
  
```csharp  
// Declare three variables; the first one is given an initial value.  
Variable<string> var1 = new Variable<string>()  
{  
    Default = "one"  
};  
Variable<string> var2 = new Variable<string>();  
Variable<string> var3 = new Variable<string>();  
  
// Define the workflow  
Activity wf = new Sequence  
{  
    Variables = { var1, var2, var3 },  
    Activities =   
    {  
        new Assign<string>()  
        {  
            Value = new InArgument<string>(var1),  
            To = new OutArgument<string>(var2)  
        },  
        new WriteLine() { Text = var2 },  
        new Assign<string>()  
        {  
            Value = var2,  
            To = var3  
        },  
        new WriteLine() { Text = var3 }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
### Использование переменных и аргументов в действиях на основе кода  
 В предыдущем примере показано использование аргументов и переменных в рабочих процессах и декларативных действиях.Аргументы и переменные также используются в действиях на основе кода.Принципы использования очень схожи.Переменные представляют хранение данных в действии, а аргументы представляют поток данных в действие и из действия и связаны создателем рабочего процесса с другими переменными или аргументами в рабочем процессе, которые представляют местоположения перемещения данных в действия и из действий.Для возврата или задания значения переменной или аргумента в действии необходимо использовать контекст действия, который представляет текущую среду выполнения действия.Он передается методу <xref:System.Activities.CodeActivity%601.Execute%2A> действия с помощью среды выполнения рабочего процесса.В этом примере настраиваемое действие `Add` определено как имеющее два аргумента <xref:System.Activities.ArgumentDirection>.Для получения доступа к значению аргументов используются метод <xref:System.Activities.Argument.Get%2A> и контекст, который был передан используемой средой выполнения рабочего процесса.  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]о работе с аргументами, переменными и выражениями в коде см. в разделах [Разработка рабочих процессов, действий и выражений с помощью императивного кода](../../../docs/framework/windows-workflow-foundation//authoring-workflows-activities-and-expressions-using-imperative-code.md) и [Обязательные аргументы и группы перегруженных аргументов](../../../docs/framework/windows-workflow-foundation//required-arguments-and-overload-groups.md).