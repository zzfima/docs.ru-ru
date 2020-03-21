---
title: Вызов проверки действия
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: 1241e6445cde20a192581e8132e563e0f7ca8d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182888"
---
# <a name="invoking-activity-validation"></a><span data-ttu-id="7cbfb-102">Вызов проверки действия</span><span class="sxs-lookup"><span data-stu-id="7cbfb-102">Invoking Activity Validation</span></span>
<span data-ttu-id="7cbfb-103">Проверка действия предоставляет метод выявления ошибок и сообщения о них в конфигурации любого действия до его выполнения.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-103">Activity validation provides a method to identify and report errors in any activity’s configuration prior to its execution.</span></span> <span data-ttu-id="7cbfb-104">Когда рабочий процесс модифицируется в конструкторе, выполняется проверка и любые ошибки или предупреждения, выявленные в ее ходе, отображаются в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-104">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="7cbfb-105">Также проверка происходит во время выполнения, когда вызывается рабочий процесс, и при появлении каких-либо ошибок проверки логикой проверки по умолчанию выдается исключение <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-105">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="7cbfb-106">Фонд рабочего процесса Windows (WF) предоставляет <xref:System.Activities.Validation.ActivityValidationServices> класс, который может быть использован приложением рабочего процесса и инструментарием разработчиков для явной проверки действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-106">Windows Workflow Foundation (WF) provides the <xref:System.Activities.Validation.ActivityValidationServices> class that can be used by workflow application and tooling developers to explicitly validate an activity.</span></span> <span data-ttu-id="7cbfb-107">В этом разделе описывается, как использовать <xref:System.Activities.Validation.ActivityValidationServices> для выполнения проверки действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-107">This topic describes how to use <xref:System.Activities.Validation.ActivityValidationServices> to perform activity validation.</span></span>  
  
## <a name="using-activityvalidationservices"></a><span data-ttu-id="7cbfb-108">Использование служб ActivityValidationServices</span><span class="sxs-lookup"><span data-stu-id="7cbfb-108">Using ActivityValidationServices</span></span>  
 <span data-ttu-id="7cbfb-109">В <xref:System.Activities.Validation.ActivityValidationServices> есть две перегруженные формы <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, используемые для вызова логики проверки действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-109"><xref:System.Activities.Validation.ActivityValidationServices> has two <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> overloads that are used to invoke an activity’s validation logic.</span></span> <span data-ttu-id="7cbfb-110">Первая перегруженная форма получает проверяемое корневое действие и возвращает коллекцию ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-110">The first overload takes the root activity to be validated and returns a collection of validation errors and warnings.</span></span> <span data-ttu-id="7cbfb-111">В следующем примере использовано пользовательское действие `Add` с двумя обязательными аргументами.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-111">In the following example, a custom `Add` activity is used that has two required arguments.</span></span>  
  
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
  
 <span data-ttu-id="7cbfb-112">Следующее действие `Add` используется внутри <xref:System.Activities.Statements.Sequence>, но два его обязательных аргумента не связаны, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-112">The `Add` activity is used inside a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound, as shown in the following example.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="7cbfb-113">Этот рабочий процесс может быть проверен путем вызова <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-113">This workflow can be validated by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="7cbfb-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> возвращает коллекцию всех ошибок и предупреждений проверки, содержащихся в действии (и в любых его дочерних действиях), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> returns a collection of any validation errors or warnings contained by the activity and any children, as shown in the following example.</span></span>  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="7cbfb-115">Когда <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> вызывается для данного образца рабочего процесса, возвращаются две выявленные при проверке ошибки.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-115">When <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> is called on this sample workflow, two validation errors are returned.</span></span>  
  
 <span data-ttu-id="7cbfb-116">**Ошибка: Не указано значение необходимого аргумента действия Operand2.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span></span>  
<span data-ttu-id="7cbfb-117">**Ошибка: Не указано значение необходимого аргумента действия Operand1.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="7cbfb-118">Если этот рабочий процесс был вызван, будет сформировано исключение <xref:System.Activities.InvalidWorkflowException>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-118">If this workflow was invoked, an <xref:System.Activities.InvalidWorkflowException> would be thrown, as shown in the following example.</span></span>  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="7cbfb-119">**System.Activities.InvalidWorkflowException:**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-119">**System.Activities.InvalidWorkflowException:**</span></span>  
<span data-ttu-id="7cbfb-120">**При обработке дерева рабочего процесса были обнаружены следующие ошибки:**
 **'Добавить': Значение для требуемого аргумента действия 'Operand2' не было поставлено.** 
 **'Добавить': Значение для требуемого аргумента деятельности 'Operand1' не было поставлено.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-120">**The following errors were encountered while processing the workflow tree:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="7cbfb-121">Чтобы данный образец рабочего процесса был действительным, два обязательных аргумента действия `Add` должны быть связаны.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-121">For this example workflow to be valid, the two required arguments of the `Add` activity must be bound.</span></span> <span data-ttu-id="7cbfb-122">В следующем примере два обязательных аргумента связаны с переменными рабочего процесса и со значением результата.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-122">In the following example, the two required arguments are bound to workflow variables along with the result value.</span></span> <span data-ttu-id="7cbfb-123">В данном примере аргумент <xref:System.Activities.Activity%601.Result%2A> связан вместе с двумя обязательными аргументами.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-123">In this example the <xref:System.Activities.Activity%601.Result%2A> argument is bound along with the two required arguments.</span></span> <span data-ttu-id="7cbfb-124">Аргумент <xref:System.Activities.Activity%601.Result%2A> связывать необязательно. Если он не связан, то при проверке это не вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-124">The <xref:System.Activities.Activity%601.Result%2A> argument is not required to be bound and does not cause a validation error if it is not.</span></span> <span data-ttu-id="7cbfb-125">В обязанности автора рабочего процесса входит связать <xref:System.Activities.Activity%601.Result%2A>, если его значение используется в другом месте рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-125">It is the responsibility of the workflow author to bind <xref:System.Activities.Activity%601.Result%2A> if its value is used elsewhere in the workflow.</span></span>  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a><span data-ttu-id="7cbfb-126">Проверка требуемых аргументов для корневого действия</span><span class="sxs-lookup"><span data-stu-id="7cbfb-126">Validating Required Arguments on the Root Activity</span></span>  
 <span data-ttu-id="7cbfb-127">Если у корневого действия рабочего процесса есть аргументы, то они не связываются, пока рабочий процесс не будет вызван и ему не будут переданы параметры.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-127">If the root activity of a workflow has arguments, these are not bound until the workflow is invoked and parameters are passed to the workflow.</span></span> <span data-ttu-id="7cbfb-128">Следующий рабочий процесс проходит проверку, но при вызове рабочего процесса без передачи обязательных аргументов создается исключение, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-128">The following workflow passes validation, but an exception is thrown if the workflow is invoked without passing in the required arguments, as shown in the following example.</span></span>  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="7cbfb-129">**System.ArgumentException: параметры аргументов корневого действия заданы неверно.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-129">**System.ArgumentException: The root activity's argument settings are incorrect.**</span></span>  
<span data-ttu-id="7cbfb-130">**Либо исправить определение рабочего процесса, либо ввести значения предложения, чтобы исправить эти ошибки:**
 **'Добавить': Значение для требуемого аргумента действия 'Operand2' не было поставлено.** 
 **'Добавить': Значение для требуемого аргумента деятельности 'Operand1' не было поставлено.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-130">**Either fix the workflow definition or supply input values to fix these errors:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="7cbfb-131">После передачи требуемых аргументов рабочий процесс будет успешно выполнен, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-131">After the correct arguments are passed, the workflow completes successfully, as shown in the following example.</span></span>  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="7cbfb-132">В данном примере корневое действие было объявлено как `Add` (вместо `Activity`), как в предыдущем примере</span><span class="sxs-lookup"><span data-stu-id="7cbfb-132">In this example, the root activity was declared as `Add` instead of `Activity` as in the previous example.</span></span> <span data-ttu-id="7cbfb-133">Это позволяет методу `WorkflowInvoker.Invoke` возвратить отдельное целочисленное значение, представляющее результаты действия `Add` вместо словаря аргументов `out`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-133">This allows the `WorkflowInvoker.Invoke` method to return a single integer that represents the results of the `Add` activity instead of a dictionary of `out` arguments.</span></span> <span data-ttu-id="7cbfb-134">Переменную `wf` также можно было объявить как `Activity<int>`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-134">The variable `wf` could also have been declared as `Activity<int>`.</span></span>  
  
 <span data-ttu-id="7cbfb-135">Во время проверки корневых аргументов базовое приложение должно проследить, чтобы при вызове рабочего процесса были переданы все обязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-135">When validating root arguments, it is the responsibility of the host application to ensure that all required arguments are passed when the workflow is invoked.</span></span>  
  
### <a name="invoking-imperative-code-based-validation"></a><span data-ttu-id="7cbfb-136">Вызов императивной проверки на уровне кода</span><span class="sxs-lookup"><span data-stu-id="7cbfb-136">Invoking Imperative Code-Based Validation</span></span>

<span data-ttu-id="7cbfb-137">Проверка в императивном коде доступна для действий, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> и <xref:System.Activities.NativeActivity>, и служит простым способом автономной проверки действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-137">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="7cbfb-138">Код проверки, определяющий все ошибки и предупреждения проверки, добавляется к действию.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-138">Validation code that determines any validation errors or warnings is added to the activity.</span></span> <span data-ttu-id="7cbfb-139">При вызове проверки допустимости для действий эти предупреждения или ошибки содержатся в коллекции, возвращаемой вызовом метода <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-139">When validation is invoked on the activity, these warnings or errors are contained in the collection returned by the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="7cbfb-140">В следующем примере определяется действие `CreateProduct` .</span><span class="sxs-lookup"><span data-stu-id="7cbfb-140">In the following example, a `CreateProduct` activity is defined.</span></span> <span data-ttu-id="7cbfb-141">Если значение `Cost` больше `Price`, к метаданным в переопределении <xref:System.Activities.CodeActivity.CacheMetadata%2A> добавляется ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-141">If the `Cost` is greater than the `Price`, a validation error is added to the metadata in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="7cbfb-142">В этом примере рабочий процесс создается с помощью действия `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-142">In this example, a workflow is configured using the `CreateProduct` activity.</span></span> <span data-ttu-id="7cbfb-143">В этом рабочем процессе `Cost` больше, чем `Price`, а обязательный аргумент `Description` не задан.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-143">In this workflow, the `Cost` is greater than the `Price`, and the required `Description` argument is not set.</span></span> <span data-ttu-id="7cbfb-144">При вызове проверки допустимости возвращаются следующие ошибки.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-144">When validation is invoked, the following errors are returned.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="7cbfb-145">**Ошибка: стоимость должна быть меньше цены или равна ей.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-145">**Error: The Cost must be less than or equal to the Price.**</span></span>  
<span data-ttu-id="7cbfb-146">**Ошибка: не указано значение необходимого аргумента действия Description.**</span><span class="sxs-lookup"><span data-stu-id="7cbfb-146">**Error: Value for a required activity argument 'Description' was not supplied.**</span></span>
> [!NOTE]
> <span data-ttu-id="7cbfb-147">Авторы настраиваемых действий могут размещать логику проверки в переопределенном методе <xref:System.Activities.CodeActivity.CacheMetadata%2A> действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-147">Custom activity authors can provide validation logic in an activity's <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="7cbfb-148">Исключения, вызванные в методе <xref:System.Activities.CodeActivity.CacheMetadata%2A>, не считаются ошибками проверки.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-148">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="7cbfb-149">Эти исключения перейдут из метода <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> к вызывающему объекту, который должен их обработать.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-149">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
## <a name="using-validationsettings"></a><span data-ttu-id="7cbfb-150">Использование ValidationSettings</span><span class="sxs-lookup"><span data-stu-id="7cbfb-150">Using ValidationSettings</span></span>  
 <span data-ttu-id="7cbfb-151">По умолчанию все действия из дерева действий вычисляются при вызове проверки службой <xref:System.Activities.Validation.ActivityValidationServices>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-151">By default, all activities in the activity tree are evaluated when validation is invoked by <xref:System.Activities.Validation.ActivityValidationServices>.</span></span> <span data-ttu-id="7cbfb-152"><xref:System.Activities.Validation.ValidationSettings> позволяет настраивать проверку несколькими способами посредством трех ее свойств.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-152"><xref:System.Activities.Validation.ValidationSettings> allows the validation to be customized in several different ways by configuring its three properties.</span></span> <span data-ttu-id="7cbfb-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> указывает, должен проверяющий элемент управления пройти по всему дереву действий или применить логику проверки только к предоставленному действию.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifies whether the validator should walk the entire activity tree or only apply validation logic to the supplied activity.</span></span> <span data-ttu-id="7cbfb-154">Значение по умолчанию для этого свойства - `false`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-154">The default for this value is `false`.</span></span> <span data-ttu-id="7cbfb-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> задает дополнительное сопоставление ограничений от типа к списку ограничений.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifies additional constraint mapping from a type to a list of constraints.</span></span> <span data-ttu-id="7cbfb-156">В <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> имеется уточняющий запрос для базового типа каждого действия из проверяемого дерева действий.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-156">For the base type of each activity in the activity tree being validated there is a lookup into <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="7cbfb-157">Если найден подходящий список ограничений, то все ограничения в нем вычисляются для действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-157">If a matching constraint list is found, all constraints in the list are evaluated for the activity.</span></span> <span data-ttu-id="7cbfb-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> указывает, должен проверяющий элемент управления вычислять все ограничения или только указанные в <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifies whether the validator should evaluate all constraints or only those specified in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="7cbfb-159">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-159">The default value is `false`.</span></span> <span data-ttu-id="7cbfb-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> и <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> помогают авторам узлов рабочих процессов добавлять дополнительные проверки рабочих процессов, например ограничения политики для таких инструментов, как FxCop.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> and <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> are useful for workflow host authors to add additional validation for workflows, such as policy constraints for tools such as FxCop.</span></span> <span data-ttu-id="7cbfb-161">Для получения дополнительной информации об ограничениях [см.](declarative-constraints.md)</span><span class="sxs-lookup"><span data-stu-id="7cbfb-161">For more information about constraints, see [Declarative Constraints](declarative-constraints.md).</span></span>  
  
 <span data-ttu-id="7cbfb-162">Чтобы использовать <xref:System.Activities.Validation.ValidationSettings>, настройте требуемые свойства и передайте этот объект в вызове <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-162">To use <xref:System.Activities.Validation.ValidationSettings>, configure the desired properties, and then pass it in the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="7cbfb-163">В данном примере проверяется рабочий процесс, состоящий из <xref:System.Activities.Statements.Sequence> с пользовательским действием `Add`.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-163">In this example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> with a custom `Add` activity is validated.</span></span> <span data-ttu-id="7cbfb-164">У действия `Add` есть два обязательных аргумента.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-164">The `Add` activity has two required arguments.</span></span>  
  
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
  
 <span data-ttu-id="7cbfb-165">Следующее действие `Add` используется в <xref:System.Activities.Statements.Sequence>, но два его обязательных аргумента не связаны.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-165">The following `Add` activity is used in a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="7cbfb-166">В следующем примере проверка выполняется, когда <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> задано значение `true`, так что проверяется только корневое действие <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-166">For the following example, validation is performed with <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> set to `true`, so only the root <xref:System.Activities.Statements.Sequence> activity is validated.</span></span>  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="7cbfb-167">Этот код отображает следующие данные.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-167">This code displays the following output:</span></span>  
  
 <span data-ttu-id="7cbfb-168">**Нет предупреждений или ошибок** Несмотря `Add` на то, что действие требует аргументов, которые не связаны, проверка является успешной, поскольку оценивается только корневая активность.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-168">**No warnings or errors** Even though the `Add` activity has required arguments that are not bound, validation is successful because only the root activity is evaluated.</span></span> <span data-ttu-id="7cbfb-169">Такой тип проверки полезен, когда нужно проверить только определенные элементы дерева действий, например изменение свойства отдельного действия в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-169">This type of validation is useful for validating only specific elements in an activity tree, such as validation of a property change of a single activity in a designer.</span></span> <span data-ttu-id="7cbfb-170">Обратите внимание, что если этот рабочий процесс вызван, то выполняется полная проверка, настроенная в рабочем процессе, и создается исключение <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-170">Note that if this workflow is invoked, the full validation configured in the workflow is evaluated and an <xref:System.Activities.InvalidWorkflowException> would be thrown.</span></span> <span data-ttu-id="7cbfb-171"><xref:System.Activities.Validation.ActivityValidationServices> и <xref:System.Activities.Validation.ValidationSettings> настраивают только проверку, явно вызываемую узлом, но невыполняемую при вызове рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7cbfb-171"><xref:System.Activities.Validation.ActivityValidationServices> and <xref:System.Activities.Validation.ValidationSettings> configure only validation explicitly invoked by the host, and not the validation that occurs when a workflow is invoked.</span></span>
