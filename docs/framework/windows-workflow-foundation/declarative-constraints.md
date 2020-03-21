---
title: Декларативные ограничения
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 321021e3d73daecae07268f33807c992414a7b4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182966"
---
# <a name="declarative-constraints"></a>Декларативные ограничения
Декларативные ограничения - это мощный метод проверки допустимости действия и его связей с другими действиями. Ограничения для действий настраиваются во время процесса создания, однако дополнительные ограничения также могут задаваться ведущим приложением рабочего процесса. В этом разделе приводятся общие сведения об использовании декларативных ограничений для обеспечения проверки допустимости действий.  
  
## <a name="using-declarative-constraints"></a>Использование декларативных ограничений  
 Ограничение - это действие, содержащее логику проверки допустимости. Это действие ограничения может быть создано в коде или в XAML. После создания действия ограничения автор действия добавляет данное ограничение в свойство <xref:System.Activities.Activity.Constraints%2A> действия, которое должно быть проверено, или использует ограничение для реализации дополнительной проверки с помощью свойства <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> экземпляра <xref:System.Activities.Validation.ValidationSettings>. Логика проверки допустимости может состоять из простых проверок допустимости, например проверки метаданных действия, но она также может выполнять проверку допустимости, учитывающую связь текущего действия с его родительскими, дочерними и одноуровневыми действиями. Ограничения создаются посредством использования действия <xref:System.Activities.Validation.Constraint%601>; кроме того, предоставляются несколько дополнительных действий проверки допустимости, облегчающие создание ошибок и предупреждений проверки допустимости и выдачу сведений о связанных действиях в рабочем процессе.  
  
### <a name="assertvalidation-and-addvalidationerror"></a>AssertValidation и AddValidationError  
 Действие <xref:System.Activities.Validation.AssertValidation> вычисляет выражение, на которое ссылается его свойство <xref:System.Activities.Validation.AssertValidation.Assertion%2A>, и, если в результате вычисления получается значение `false`, к <xref:System.Activities.Validation.ValidationResults> добавляется ошибка или предупреждение проверки допустимости. Свойство <xref:System.Activities.Validation.AssertValidation.Message%2A> описывает ошибку проверки допустимости; свойство <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> указывает, является ли неудачная проверка допустимости ошибкой или предупреждением. По умолчанию для объекта <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> установлено значение `false`.  
  
 В следующем примере объявляется ограничение, возвращающее предупреждение проверки допустимости, если длина <xref:System.Activities.Activity.DisplayName%2A> действия, для которого выполняется проверка, меньше или равна двум символам. Параметр универсального типа, используемый для <xref:System.Activities.Validation.Constraint%601>, задает тип действия, проверяемого ограничением. Это ограничение использует действие <xref:System.Activities.Activity> в качестве универсального типа. Оно может использоваться для проверки допустимости всех типов действий.  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 Чтобы задать данное ограничение для действия, его следует добавить в <xref:System.Activities.Activity.Constraints%2A> для действия, как показано в следующем примере кода.  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 Ведущее приложение может также задавать это ограничение для действий в рабочем процессе посредством использования <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. Этот вариант описывается в следующем разделе.  
  
 Действие <xref:System.Activities.Validation.AddValidationError> используется для создания ошибки или предупреждения проверки допустимости без необходимости вычисления выражения. Его свойства подобны свойствам <xref:System.Activities.Validation.AssertValidation>; оно может использоваться совместно с действиями управления потоком ограничения, например с действием <xref:System.Activities.Statements.If>.
  
### <a name="workflow-relationship-activities"></a>Действия связей рабочих процессов

Доступны несколько действий проверки допустимости, которые предоставляют сведения о других действиях в рабочем процессе относительно проверяемого действия. <xref:System.Activities.Validation.GetParentChain> возвращает коллекцию действий, содержащую все действия, лежащие между текущим и корневым действиями. <xref:System.Activities.Validation.GetChildSubtree> предоставляет коллекцию действий, содержащую дочерние действия в рекурсивном шаблоне, и <xref:System.Activities.Validation.GetWorkflowTree> возвращает все действия в рабочем процессе.  
  
В следующем примере определяется действие `CreateState` . Действие `CreateState` должно содержаться в действии `CreateCountry`; метод `GetParent` возвращает ограничение, принудительно реализующее это требование. `GetParent` использует действие <xref:System.Activities.Validation.GetParentChain> совместно с действием <xref:System.Activities.Statements.ForEach%601> для проверки родительских действий действия `CreateState`, чтобы определить, удовлетворяется ли это требование.  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {
            Body = new ActivityAction<CreateState,ValidationContext>  
            {
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context
                            },  
                            Body = new ActivityAction<Activity>  
                            {
                                Argument = parent,
                                Handler = new If()  
                                {
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a>Дополнительные ограничения  
 Авторы ведущих приложений рабочих процессов могут задавать дополнительные ограничения проверки допустимости для действий в рабочем процессе, создавая ограничения и добавляя их к словарю <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> экземпляра <xref:System.Activities.Validation.ValidationSettings>. Каждый элемент в <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> содержит тип действия, к которому применяются ограничения, а также список дополнительных ограничений для этого типа действия. При вызове проверки допустимости для рабочего процесса каждое действие указанного типа, включая производные классы, проверяется на соответствие ограничениям. В этом примере ограничение `ActivityDisplayNameIsNotSetWarning` из предыдущего раздела применяется ко всем действиям в рабочем процессе.  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 Если свойство <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> у <xref:System.Activities.Validation.ValidationSettings> имеет значение `true`, то при вызове проверки допустимости путем вызова <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> выполняется проверка только дополнительных ограничений. Это может быть полезно при проверке рабочих процессов по отдельным конфигурациям проверки. Необходимо отметить, что при вызове рабочего процесса выполняется проверка логики проверки, настроенной в рабочем процессе; для запуска рабочего процесса проверка должна быть пройдена успешно. Для получения дополнительной информации о вызывая проверку [см.](invoking-activity-validation.md)
