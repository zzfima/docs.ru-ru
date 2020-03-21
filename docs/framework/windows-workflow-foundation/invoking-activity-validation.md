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
# <a name="invoking-activity-validation"></a>Вызов проверки действия
Проверка действия предоставляет метод выявления ошибок и сообщения о них в конфигурации любого действия до его выполнения. Когда рабочий процесс модифицируется в конструкторе, выполняется проверка и любые ошибки или предупреждения, выявленные в ее ходе, отображаются в конструкторе. Также проверка происходит во время выполнения, когда вызывается рабочий процесс, и при появлении каких-либо ошибок проверки логикой проверки по умолчанию выдается исключение <xref:System.Activities.InvalidWorkflowException>. Фонд рабочего процесса Windows (WF) предоставляет <xref:System.Activities.Validation.ActivityValidationServices> класс, который может быть использован приложением рабочего процесса и инструментарием разработчиков для явной проверки действия. В этом разделе описывается, как использовать <xref:System.Activities.Validation.ActivityValidationServices> для выполнения проверки действия.  
  
## <a name="using-activityvalidationservices"></a>Использование служб ActivityValidationServices  
 В <xref:System.Activities.Validation.ActivityValidationServices> есть две перегруженные формы <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, используемые для вызова логики проверки действия. Первая перегруженная форма получает проверяемое корневое действие и возвращает коллекцию ошибок и предупреждений. В следующем примере использовано пользовательское действие `Add` с двумя обязательными аргументами.  
  
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
  
 Следующее действие `Add` используется внутри <xref:System.Activities.Statements.Sequence>, но два его обязательных аргумента не связаны, как показано в следующем примере.  
  
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
  
 Этот рабочий процесс может быть проверен путем вызова <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> возвращает коллекцию всех ошибок и предупреждений проверки, содержащихся в действии (и в любых его дочерних действиях), как показано в следующем примере.  
  
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
  
 Когда <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> вызывается для данного образца рабочего процесса, возвращаются две выявленные при проверке ошибки.  
  
 **Ошибка: Не указано значение необходимого аргумента действия Operand2.**  
**Ошибка: Не указано значение необходимого аргумента действия Operand1.**  Если этот рабочий процесс был вызван, будет сформировано исключение <xref:System.Activities.InvalidWorkflowException>, как показано в следующем примере.  
  
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
  
 **System.Activities.InvalidWorkflowException:**  
**При обработке дерева рабочего процесса были обнаружены следующие ошибки:**
 **'Добавить': Значение для требуемого аргумента действия 'Operand2' не было поставлено.** 
 **'Добавить': Значение для требуемого аргумента деятельности 'Operand1' не было поставлено.**  Чтобы данный образец рабочего процесса был действительным, два обязательных аргумента действия `Add` должны быть связаны. В следующем примере два обязательных аргумента связаны с переменными рабочего процесса и со значением результата. В данном примере аргумент <xref:System.Activities.Activity%601.Result%2A> связан вместе с двумя обязательными аргументами. Аргумент <xref:System.Activities.Activity%601.Result%2A> связывать необязательно. Если он не связан, то при проверке это не вызовет ошибку. В обязанности автора рабочего процесса входит связать <xref:System.Activities.Activity%601.Result%2A>, если его значение используется в другом месте рабочего процесса.  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a>Проверка требуемых аргументов для корневого действия  
 Если у корневого действия рабочего процесса есть аргументы, то они не связываются, пока рабочий процесс не будет вызван и ему не будут переданы параметры. Следующий рабочий процесс проходит проверку, но при вызове рабочего процесса без передачи обязательных аргументов создается исключение, как показано в следующем примере.  
  
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
  
 **System.ArgumentException: параметры аргументов корневого действия заданы неверно.**  
**Либо исправить определение рабочего процесса, либо ввести значения предложения, чтобы исправить эти ошибки:**
 **'Добавить': Значение для требуемого аргумента действия 'Operand2' не было поставлено.** 
 **'Добавить': Значение для требуемого аргумента деятельности 'Operand1' не было поставлено.**  После передачи требуемых аргументов рабочий процесс будет успешно выполнен, как показано в следующем примере.  
  
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
> В данном примере корневое действие было объявлено как `Add` (вместо `Activity`), как в предыдущем примере Это позволяет методу `WorkflowInvoker.Invoke` возвратить отдельное целочисленное значение, представляющее результаты действия `Add` вместо словаря аргументов `out`. Переменную `wf` также можно было объявить как `Activity<int>`.  
  
 Во время проверки корневых аргументов базовое приложение должно проследить, чтобы при вызове рабочего процесса были переданы все обязательные аргументы.  
  
### <a name="invoking-imperative-code-based-validation"></a>Вызов императивной проверки на уровне кода

Проверка в императивном коде доступна для действий, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> и <xref:System.Activities.NativeActivity>, и служит простым способом автономной проверки действия. Код проверки, определяющий все ошибки и предупреждения проверки, добавляется к действию. При вызове проверки допустимости для действий эти предупреждения или ошибки содержатся в коллекции, возвращаемой вызовом метода <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. В следующем примере определяется действие `CreateProduct` . Если значение `Cost` больше `Price`, к метаданным в переопределении <xref:System.Activities.CodeActivity.CacheMetadata%2A> добавляется ошибка проверки.  
  
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
  
 В этом примере рабочий процесс создается с помощью действия `CreateProduct`. В этом рабочем процессе `Cost` больше, чем `Price`, а обязательный аргумент `Description` не задан. При вызове проверки допустимости возвращаются следующие ошибки.  
  
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
  
 **Ошибка: стоимость должна быть меньше цены или равна ей.**  
**Ошибка: не указано значение необходимого аргумента действия Description.**
> [!NOTE]
> Авторы настраиваемых действий могут размещать логику проверки в переопределенном методе <xref:System.Activities.CodeActivity.CacheMetadata%2A> действия. Исключения, вызванные в методе <xref:System.Activities.CodeActivity.CacheMetadata%2A>, не считаются ошибками проверки. Эти исключения перейдут из метода <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> к вызывающему объекту, который должен их обработать.  
  
## <a name="using-validationsettings"></a>Использование ValidationSettings  
 По умолчанию все действия из дерева действий вычисляются при вызове проверки службой <xref:System.Activities.Validation.ActivityValidationServices>. <xref:System.Activities.Validation.ValidationSettings> позволяет настраивать проверку несколькими способами посредством трех ее свойств. <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> указывает, должен проверяющий элемент управления пройти по всему дереву действий или применить логику проверки только к предоставленному действию. Значение по умолчанию для этого свойства - `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> задает дополнительное сопоставление ограничений от типа к списку ограничений. В <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> имеется уточняющий запрос для базового типа каждого действия из проверяемого дерева действий. Если найден подходящий список ограничений, то все ограничения в нем вычисляются для действия. <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> указывает, должен проверяющий элемент управления вычислять все ограничения или только указанные в <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. Значение по умолчанию — `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> и <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> помогают авторам узлов рабочих процессов добавлять дополнительные проверки рабочих процессов, например ограничения политики для таких инструментов, как FxCop. Для получения дополнительной информации об ограничениях [см.](declarative-constraints.md)  
  
 Чтобы использовать <xref:System.Activities.Validation.ValidationSettings>, настройте требуемые свойства и передайте этот объект в вызове <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. В данном примере проверяется рабочий процесс, состоящий из <xref:System.Activities.Statements.Sequence> с пользовательским действием `Add`. У действия `Add` есть два обязательных аргумента.  
  
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
  
 Следующее действие `Add` используется в <xref:System.Activities.Statements.Sequence>, но два его обязательных аргумента не связаны.  
  
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
  
 В следующем примере проверка выполняется, когда <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> задано значение `true`, так что проверяется только корневое действие <xref:System.Activities.Statements.Sequence>.  
  
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
  
 Этот код отображает следующие данные.  
  
 **Нет предупреждений или ошибок** Несмотря `Add` на то, что действие требует аргументов, которые не связаны, проверка является успешной, поскольку оценивается только корневая активность. Такой тип проверки полезен, когда нужно проверить только определенные элементы дерева действий, например изменение свойства отдельного действия в конструкторе. Обратите внимание, что если этот рабочий процесс вызван, то выполняется полная проверка, настроенная в рабочем процессе, и создается исключение <xref:System.Activities.InvalidWorkflowException>. <xref:System.Activities.Validation.ActivityValidationServices> и <xref:System.Activities.Validation.ValidationSettings> настраивают только проверку, явно вызываемую узлом, но невыполняемую при вызове рабочего процесса.
