---
title: Принудительная проверка на уровне кода
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: f3b07d0ab06b3753286c929b90e713a6941684ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143100"
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="35a05-102">Принудительная проверка на уровне кода</span><span class="sxs-lookup"><span data-stu-id="35a05-102">Imperative Code-Based Validation</span></span>

<span data-ttu-id="35a05-103">Проверка в императивном коде доступна для действий, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> и <xref:System.Activities.NativeActivity>, и служит простым способом автономной проверки действия.</span><span class="sxs-lookup"><span data-stu-id="35a05-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="35a05-104">Код проверки, определяющий все ошибки и предупреждения проверки, добавляется к действию.</span><span class="sxs-lookup"><span data-stu-id="35a05-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="35a05-105">Использование проверки на основе кода</span><span class="sxs-lookup"><span data-stu-id="35a05-105">Using Code-Based Validation</span></span>

<span data-ttu-id="35a05-106">Проверка на основе кода поддерживается действиями, которые являются производными от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> и <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="35a05-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="35a05-107">Код проверки можно поместить в переопределение метода <xref:System.Activities.CodeActivity.CacheMetadata%2A>, при этом ошибки и предупреждения проверки могут быть добавлены к аргументу метаданных.</span><span class="sxs-lookup"><span data-stu-id="35a05-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="35a05-108">В следующем примере, если значение `Cost` больше `Price`, к метаданным добавляется ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="35a05-108">In the following example, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35a05-109">Обратите внимание, что `Cost` и `Price` являются не аргументами для действия, а свойствами, задаваемыми во время разработки.</span><span class="sxs-lookup"><span data-stu-id="35a05-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="35a05-110">Поэтому их значения можно проверить в переопределенном методе действия <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="35a05-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="35a05-111">Значение потока данных, проходящее через аргумент, не может быть проверено во время разработки, поскольку данные не будут поступать до времени выполнения, но аргументы действия можно проверить, чтобы убедиться, что они связаны, с помощью атрибута `RequiredArgument` и групп перегруженных вариантов.</span><span class="sxs-lookup"><span data-stu-id="35a05-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="35a05-112">В этом примере код видит атрибут `RequiredArgument` для аргумента `Description` и, если он не связан, формируется ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="35a05-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="35a05-113">Требуемые аргументы рассматриваются в [группах «Требуемые аргументы» и «Перегрузка».](required-arguments-and-overload-groups.md)</span><span class="sxs-lookup"><span data-stu-id="35a05-113">Required arguments are covered in [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>  
  
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
  
 <span data-ttu-id="35a05-114">По умолчанию ошибка проверки добавляется к метаданным при вызове <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>.</span><span class="sxs-lookup"><span data-stu-id="35a05-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="35a05-115">Чтобы добавить предупреждение проверки, используйте перегрузку <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>, принимающую <xref:System.Activities.Validation.ValidationError>, и укажите, что <xref:System.Activities.Validation.ValidationError> представляет предупреждение, задав свойство <xref:System.Activities.Validation.ValidationError.IsWarning%2A>.</span><span class="sxs-lookup"><span data-stu-id="35a05-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="35a05-116">Когда рабочий процесс модифицируется в конструкторе, выполняется проверка и любые ошибки или предупреждения, выявленные в ее ходе, отображаются в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="35a05-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="35a05-117">Также проверка происходит во время выполнения, когда вызывается рабочий процесс, и при появлении каких-либо ошибок проверки логикой проверки по умолчанию выдается исключение <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="35a05-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="35a05-118">Для получения дополнительной информации о вызывая проверку и доступ к любым предупреждениям или ошибкам проверки, [см.](invoking-activity-validation.md)</span><span class="sxs-lookup"><span data-stu-id="35a05-118">For more information about invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="35a05-119">Исключения, вызванные в методе <xref:System.Activities.CodeActivity.CacheMetadata%2A>, не считаются ошибками проверки.</span><span class="sxs-lookup"><span data-stu-id="35a05-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="35a05-120">Эти исключения перейдут из метода <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> к вызывающему объекту, который должен их обработать.</span><span class="sxs-lookup"><span data-stu-id="35a05-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="35a05-121">Проверка на основе кода используется для проверки действий, которые содержат код, но для нее недоступны другие действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="35a05-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="35a05-122">Декларативная проверка ограничений обеспечивает возможность проверки взаимосвязи между деятельностью и другими действиями в рабочем процессе и рассматривается в теме [Декларативных ограничений.](declarative-constraints.md)</span><span class="sxs-lookup"><span data-stu-id="35a05-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](declarative-constraints.md) topic.</span></span>
