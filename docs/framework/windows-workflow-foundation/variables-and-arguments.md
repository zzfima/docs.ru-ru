---
title: Переменные и аргументы
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: f975f46a1858d204d12588f7570b7ea5a365e650
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182683"
---
# <a name="variables-and-arguments"></a><span data-ttu-id="93660-102">Переменные и аргументы</span><span class="sxs-lookup"><span data-stu-id="93660-102">Variables and Arguments</span></span>
<span data-ttu-id="93660-103">В Фонде рабочего процесса Windows (WF) переменные представляют собой хранение данных, а аргументы представляют поток данных в действие и из нее.</span><span class="sxs-lookup"><span data-stu-id="93660-103">In Windows Workflow Foundation (WF), variables represent the storage of data and arguments represent the flow of data into and out of an activity.</span></span> <span data-ttu-id="93660-104">Действие имеет набор аргументов, которые составляют сигнатуру действия.</span><span class="sxs-lookup"><span data-stu-id="93660-104">An activity has a set of arguments and they make up the signature of the activity.</span></span> <span data-ttu-id="93660-105">Действие может также поддерживать список переменных, к которым разработчик может добавлять или удалять переменные при разработке рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="93660-105">Additionally, an activity can maintain a list of variables to which a developer can add or remove variables during the design of a workflow.</span></span> <span data-ttu-id="93660-106">Привязка аргумента выполнена с помощью выражения, возвращающего значение.</span><span class="sxs-lookup"><span data-stu-id="93660-106">An argument is bound using an expression that returns a value.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="93660-107">Переменные</span><span class="sxs-lookup"><span data-stu-id="93660-107">Variables</span></span>  
 <span data-ttu-id="93660-108">Переменные представляют собой место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="93660-108">Variables are storage locations for data.</span></span> <span data-ttu-id="93660-109">Переменные объявляются в составе определения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="93660-109">Variables are declared as part of the definition of a workflow.</span></span> <span data-ttu-id="93660-110">Переменные принимают значения во время выполнения, и эти значения сохраняются как часть состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="93660-110">Variables take on values at runtime and these values are stored as part of the state of a workflow instance.</span></span> <span data-ttu-id="93660-111">Определение переменной указывает тип переменной и, возможно, имя.</span><span class="sxs-lookup"><span data-stu-id="93660-111">A variable definition specifies the type of the variable and optionally, the name.</span></span> <span data-ttu-id="93660-112">В следующем коде показано, как объявить переменную, присвоить ей значение с помощью действия <xref:System.Activities.Statements.Assign%601>, а затем отобразить ее значение на консоли с помощью действия <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="93660-112">The following code shows how to declare a variable, assign a value to it using an <xref:System.Activities.Statements.Assign%601> activity, and then display its value to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
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
  
 <span data-ttu-id="93660-113">Выражение значения по умолчанию может быть дополнительно указано как часть объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="93660-113">A default value expression can optionally be specified as part of a variable declaration.</span></span> <span data-ttu-id="93660-114">У переменных также имеются модификаторы.</span><span class="sxs-lookup"><span data-stu-id="93660-114">Variables also can have modifiers.</span></span> <span data-ttu-id="93660-115">Например, если переменная доступна только для чтения, то можно применить модификатор, доступный только для чтения <xref:System.Activities.VariableModifiers>.</span><span class="sxs-lookup"><span data-stu-id="93660-115">For example, if a variable is read-only then the read-only <xref:System.Activities.VariableModifiers> modifier can be applied.</span></span> <span data-ttu-id="93660-116">В следующем примере создается доступная только для чтения переменная, для которой задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93660-116">In the following example, a read-only variable is created that has a default value assigned.</span></span>  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a><span data-ttu-id="93660-117">Определение областей переменных</span><span class="sxs-lookup"><span data-stu-id="93660-117">Variable Scoping</span></span>  
 <span data-ttu-id="93660-118">Время существования переменной во время выполнения равно времени существования действия, которое объявило эту переменную.</span><span class="sxs-lookup"><span data-stu-id="93660-118">The lifetime of a variable at runtime is equal to the lifetime of the activity that declares it.</span></span> <span data-ttu-id="93660-119">После завершения действия выполняется очистка его переменных, после чего нельзя больше ссылаться на эти переменные.</span><span class="sxs-lookup"><span data-stu-id="93660-119">When an activity completes, its variables are cleaned up and can no longer be referenced.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="93660-120">Аргументы</span><span class="sxs-lookup"><span data-stu-id="93660-120">Arguments</span></span>  
 <span data-ttu-id="93660-121">Создатели действия используют аргументы для определения способов перемещения данных в действие и из действия.</span><span class="sxs-lookup"><span data-stu-id="93660-121">Activity authors use arguments to define the way data flows into and out of an activity.</span></span> <span data-ttu-id="93660-122">Все аргументы имеют указанные направления: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> или <xref:System.Activities.ArgumentDirection.InOut>.</span><span class="sxs-lookup"><span data-stu-id="93660-122">Each argument has a specified direction: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, or <xref:System.Activities.ArgumentDirection.InOut>.</span></span>  
  
 <span data-ttu-id="93660-123">Среда выполнения рабочих процессов обеспечивает выполнение следующих условий, касающихся времени перемещения данных в действия и из действий:</span><span class="sxs-lookup"><span data-stu-id="93660-123">The workflow runtime makes the following guarantees about the timing of data movement into and out of activities:</span></span>  
  
1. <span data-ttu-id="93660-124">После начала выполнения действия рассчитываются значения всех входных и входных/выходных аргументов.</span><span class="sxs-lookup"><span data-stu-id="93660-124">When an activity starts executing, the values of all of its input and input/output arguments are calculated.</span></span> <span data-ttu-id="93660-125">Например, независимо от времени вызова <xref:System.Activities.Argument.Get%2A> возвращается значение, которое рассчитывается средой выполнения до его вызова `Execute`.</span><span class="sxs-lookup"><span data-stu-id="93660-125">For example, regardless of when <xref:System.Activities.Argument.Get%2A> is called, the value returned is the one calculated by the runtime prior to its invocation of `Execute`.</span></span>  
  
2. <span data-ttu-id="93660-126">При вызове <xref:System.Activities.InOutArgument%601.Set%2A> среда выполнения немедленно задает значение.</span><span class="sxs-lookup"><span data-stu-id="93660-126">When <xref:System.Activities.InOutArgument%601.Set%2A> is called, the runtime sets the value immediately.</span></span>  
  
3. <span data-ttu-id="93660-127">Для аргументов может быть дополнительно задан их <xref:System.Activities.Argument.EvaluationOrder%2A>.</span><span class="sxs-lookup"><span data-stu-id="93660-127">Arguments can optionally have their <xref:System.Activities.Argument.EvaluationOrder%2A> specified.</span></span> <span data-ttu-id="93660-128"><xref:System.Activities.Argument.EvaluationOrder%2A> - отсчитываемое от нуля значение, которое указывает порядок вычисления аргумента.</span><span class="sxs-lookup"><span data-stu-id="93660-128"><xref:System.Activities.Argument.EvaluationOrder%2A> is a zero-based value that specifies the order in which the argument is evaluated.</span></span> <span data-ttu-id="93660-129">По умолчанию порядок вычисления аргумента не указан и равен значению <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>.</span><span class="sxs-lookup"><span data-stu-id="93660-129">By default, the evaluation order of the argument is unspecified and is equal to the <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> value.</span></span> <span data-ttu-id="93660-130">Свойству <xref:System.Activities.Argument.EvaluationOrder%2A> задайте значение, большее или равное нулю, чтобы указать порядок вычисления для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="93660-130">Set <xref:System.Activities.Argument.EvaluationOrder%2A> to a value greater or equal to zero to specify an evaluation order for this argument.</span></span> <span data-ttu-id="93660-131">Фонд Рабочего процесса Windows оценивает аргументы с указанным порядком оценки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="93660-131">Windows Workflow Foundation evaluates arguments with a specified evaluation order in ascending order.</span></span> <span data-ttu-id="93660-132">Следует отметить, что аргументы с незаданным порядком вычисления вычисляются до вычисления аргументов, порядок вычисления которых задан.</span><span class="sxs-lookup"><span data-stu-id="93660-132">Note that arguments with an unspecified evaluation order are evaluated before those with a specified evaluation order.</span></span>  
  
 <span data-ttu-id="93660-133">Создатель действия для предоставления доступа к аргументам действия может использовать механизм со строгой типизацией.</span><span class="sxs-lookup"><span data-stu-id="93660-133">An activity author can use a strongly-typed mechanism for exposing its arguments.</span></span> <span data-ttu-id="93660-134">Для этого объявляются свойства типа <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> и <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="93660-134">This is accomplished by declaring properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="93660-135">Благодаря этому для создателя действия обеспечивается возможность установки определенного контракта, касающегося потока данных в действие и из действия.</span><span class="sxs-lookup"><span data-stu-id="93660-135">This allows an activity author to establish a specific contract about the data going into and out of an activity.</span></span>  
  
### <a name="defining-the-arguments-on-an-activity"></a><span data-ttu-id="93660-136">Определение аргументов для действия</span><span class="sxs-lookup"><span data-stu-id="93660-136">Defining the Arguments on an Activity</span></span>  
 <span data-ttu-id="93660-137">Для действия можно определить аргументы путем указания свойств типа <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> и <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="93660-137">Arguments can be defined on an activity by specifying properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="93660-138">В следующем коде показано определение аргументов для действия `Prompt`, принимающего строку для отображения для пользователя и возвращающего строку, которая содержит ответ пользователя.</span><span class="sxs-lookup"><span data-stu-id="93660-138">The following code shows how to define the arguments for a `Prompt` activity that takes in a string to display to the user and returns a string that contains the user's response.</span></span>  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="93660-139">Действия, которые возвращают одно значение, могут быть производными от <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> или <xref:System.Activities.CodeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="93660-139">Activities that return a single value can derive from <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, or <xref:System.Activities.CodeActivity%601>.</span></span> <span data-ttu-id="93660-140">У этих действий существует полностью определенный аргумент <xref:System.Activities.OutArgument%601> с именем <xref:System.Activities.Activity%601.Result%2A>, который содержит возвращаемое значение действия.</span><span class="sxs-lookup"><span data-stu-id="93660-140">These activities have a well-defined <xref:System.Activities.OutArgument%601> named <xref:System.Activities.Activity%601.Result%2A> that contains the return value of the activity.</span></span>  
  
### <a name="using-variables-and-arguments-in-workflows"></a><span data-ttu-id="93660-141">Использование переменных и аргументов в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="93660-141">Using Variables and Arguments in Workflows</span></span>  
 <span data-ttu-id="93660-142">В следующем примере показано, как переменные и аргументы используются в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="93660-142">The following example shows how variables and arguments are used in a workflow.</span></span> <span data-ttu-id="93660-143">Рабочий процесс представляет собой последовательность, объявляющую три переменные: `var1`, `var2` и `var3`.</span><span class="sxs-lookup"><span data-stu-id="93660-143">The workflow is a sequence that declares three variables: `var1`, `var2`, and `var3`.</span></span> <span data-ttu-id="93660-144">Первым действием в рабочем процессе является действие `Assign`, которое присваивает значение переменной `var1` переменной `var2`.</span><span class="sxs-lookup"><span data-stu-id="93660-144">The first activity in the workflow is an `Assign` activity that assigns the value of variable `var1` to the variable `var2`.</span></span> <span data-ttu-id="93660-145">За этим следует действие `WriteLine`, выполняющее печать значения переменной `var2`.</span><span class="sxs-lookup"><span data-stu-id="93660-145">This is followed by a `WriteLine` activity that prints the value of the `var2` variable.</span></span> <span data-ttu-id="93660-146">Затем следует еще одно действие `Assign`, которое присваивает значение переменной `var2` переменной `var3`.</span><span class="sxs-lookup"><span data-stu-id="93660-146">Next is another `Assign` activity that assigns the value of variable `var2` to the variable `var3`.</span></span> <span data-ttu-id="93660-147">И, наконец, существует еще одно действие `WriteLine`, выполняющее печать значения переменной `var3`.</span><span class="sxs-lookup"><span data-stu-id="93660-147">Finally there is another `WriteLine` activity that prints the value of the `var3` variable.</span></span> <span data-ttu-id="93660-148">Первое действие `Assign` использует объекты `InArgument<string>` и `OutArgument<string>`, которые явно представляют привязки аргументов действия.</span><span class="sxs-lookup"><span data-stu-id="93660-148">The first `Assign` activity uses `InArgument<string>` and `OutArgument<string>` objects that explicitly represent the bindings for the activity's arguments.</span></span> <span data-ttu-id="93660-149">`InArgument<string>` используется для <xref:System.Activities.Statements.Assign.Value%2A>, поскольку значение передается действию <xref:System.Activities.Statements.Assign%601> с помощью его аргумента <xref:System.Activities.Statements.Assign.Value%2A>, а `OutArgument<string>` используется для <xref:System.Activities.Statements.Assign.To%2A>, так как значение передается от аргумента <xref:System.Activities.Statements.Assign.To%2A> переменной.</span><span class="sxs-lookup"><span data-stu-id="93660-149">`InArgument<string>` is used for <xref:System.Activities.Statements.Assign.Value%2A> because the value is flowing into the <xref:System.Activities.Statements.Assign%601> activity through its <xref:System.Activities.Statements.Assign.Value%2A> argument, and `OutArgument<string>` is used for <xref:System.Activities.Statements.Assign.To%2A> because the value is flowing out of the <xref:System.Activities.Statements.Assign.To%2A> argument into the variable.</span></span> <span data-ttu-id="93660-150">Второе действие `Assign` позволяет добиться такого же результата с использованием более компактного, но аналогичного синтаксиса, в котором используются явные операции приведения.</span><span class="sxs-lookup"><span data-stu-id="93660-150">The second `Assign` activity accomplishes the same thing with more compact but equivalent syntax that uses implicit casts.</span></span> <span data-ttu-id="93660-151">Действия `WriteLine` также используют компактный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="93660-151">The `WriteLine` activities also use the compact syntax.</span></span>  
  
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
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a><span data-ttu-id="93660-152">Использование переменных и аргументов в действиях на основе кода</span><span class="sxs-lookup"><span data-stu-id="93660-152">Using Variables and Arguments in Code-Based Activities</span></span>  
 <span data-ttu-id="93660-153">В предыдущем примере показано использование аргументов и переменных в рабочих процессах и декларативных действиях.</span><span class="sxs-lookup"><span data-stu-id="93660-153">The previous examples show how to use arguments and variables in workflows and declarative activities.</span></span> <span data-ttu-id="93660-154">Аргументы и переменные также используются в действиях на основе кода.</span><span class="sxs-lookup"><span data-stu-id="93660-154">Arguments and variables are also used in code-based activities.</span></span> <span data-ttu-id="93660-155">Принципы использования очень схожи.</span><span class="sxs-lookup"><span data-stu-id="93660-155">Conceptually the usage is very similar.</span></span> <span data-ttu-id="93660-156">Переменные представляют хранение данных в действии, а аргументы представляют поток данных в действие и из действия и связаны создателем рабочего процесса с другими переменными или аргументами в рабочем процессе, которые представляют местоположения перемещения данных в действия и из действий.</span><span class="sxs-lookup"><span data-stu-id="93660-156">Variables represent data storage within the activity, and arguments represent the flow of data into or out of the activity, and are bound by the workflow author to other variables or arguments in the workflow that represent where the data flows to or from.</span></span> <span data-ttu-id="93660-157">Для возврата или задания значения переменной или аргумента в действии необходимо использовать контекст действия, который представляет текущую среду выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="93660-157">To get or set the value of a variable or argument in an activity, an activity context must be used that represents the current execution environment of the activity.</span></span> <span data-ttu-id="93660-158">Он передается методу <xref:System.Activities.CodeActivity%601.Execute%2A> действия с помощью среды выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="93660-158">This is passed into the <xref:System.Activities.CodeActivity%601.Execute%2A> method of the activity by the workflow runtime.</span></span> <span data-ttu-id="93660-159">В этом примере настраиваемое действие `Add` определено как имеющее два аргумента <xref:System.Activities.ArgumentDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="93660-159">In this example, a custom `Add` activity is defined that has two <xref:System.Activities.ArgumentDirection.In> arguments.</span></span> <span data-ttu-id="93660-160">Для получения доступа к значению аргументов используются метод <xref:System.Activities.Argument.Get%2A> и контекст, который был передан используемой средой выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="93660-160">To access the value of the arguments, the <xref:System.Activities.Argument.Get%2A> method is used and the context that was passed in by the workflow runtime is used.</span></span>  
  
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
  
 <span data-ttu-id="93660-161">Для получения дополнительной информации о работе с аргументами, переменными и выражениями в коде [см.](authoring-workflows-activities-and-expressions-using-imperative-code.md) [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md)</span><span class="sxs-lookup"><span data-stu-id="93660-161">For more information about working with arguments, variables, and expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) and [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>
