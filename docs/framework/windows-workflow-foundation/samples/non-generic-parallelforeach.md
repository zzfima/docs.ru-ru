---
title: Не универсальный ParallelForEach
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 33e0c8ef8c04b7d58815760ae1152f63891fdfd5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715647"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="dc98f-102">Не универсальный ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="dc98f-102">Non-generic ParallelForEach</span></span>

<span data-ttu-id="dc98f-103">В область элементов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] входит набор действий потока управления, включая элемент <xref:System.Activities.Statements.ParallelForEach%601>, который позволяет проходить по коллекциям <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>

<span data-ttu-id="dc98f-104">для <xref:System.Activities.Statements.ParallelForEach%601> требуется, чтобы свойство <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> было типа <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type  <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="dc98f-105">Это запрещает пользователям проходить по структурам данных, в которых реализован интерфейс <xref:System.Collections.Generic.IEnumerable%601> (например, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="dc98f-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="dc98f-106">Неуниверсальная версия <xref:System.Activities.Statements.ParallelForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="dc98f-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>

<span data-ttu-id="dc98f-107">В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ParallelForEach%601> и конструктор для него.</span><span class="sxs-lookup"><span data-stu-id="dc98f-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="dc98f-108">Это действие позволяет проходить по <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>

## <a name="parallelforeach-activity"></a><span data-ttu-id="dc98f-109">Действие ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="dc98f-109">ParallelForEach activity</span></span>

<span data-ttu-id="dc98f-110">Оператор `foreach` в C# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="dc98f-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="dc98f-111">Эквивалентными действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="dc98f-112">Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое.</span><span class="sxs-lookup"><span data-stu-id="dc98f-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="dc98f-113">Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.</span><span class="sxs-lookup"><span data-stu-id="dc98f-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>

<span data-ttu-id="dc98f-114"><xref:System.Activities.Statements.ParallelForEach%601> имеет <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, поэтому действие <xref:System.Activities.Statements.ParallelForEach%601> может завершиться рано, если оценка <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вернет результат `true`.</span><span class="sxs-lookup"><span data-stu-id="dc98f-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="dc98f-115">Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="dc98f-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>

<span data-ttu-id="dc98f-116">Для большинства случаев универсальная версия действия является предпочтительным вариантом, поскольку он охватывает большинство сценариев, в которых используется действие, и предоставляет проверку соответствия типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="dc98f-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="dc98f-117">Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>

## <a name="class-definition"></a><span data-ttu-id="dc98f-118">Определение класса</span><span class="sxs-lookup"><span data-stu-id="dc98f-118">Class definition</span></span>

<span data-ttu-id="dc98f-119">В следующем примере кода показано определение неуниверсального действия `ParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="dc98f-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>

```csharp
[ContentProperty("Body")]
public class ParallelForEach : NativeActivity
{
    [RequiredArgument]
    [DefaultValue(null)]
    InArgument<IEnumerable> Values { get; set; }

    [DefaultValue(null)]
    [DependsOn("Values")]
    public Activity<bool> CompletionCondition
    [DefaultValue(null)]
    [DependsOn("CompletionCondition")]
    ActivityAction<object> Body { get; set; }
}
```

<span data-ttu-id="dc98f-120">Текст (необязательно) </span><span class="sxs-lookup"><span data-stu-id="dc98f-120">Body (optional)</span></span>\
<span data-ttu-id="dc98f-121">Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="dc98f-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="dc98f-122">Каждый отдельный элемент передается в текст через свойство Argument.</span><span class="sxs-lookup"><span data-stu-id="dc98f-122">Each individual element is passed into the Body through its Argument property.</span></span>

<span data-ttu-id="dc98f-123">Значения (необязательно) </span><span class="sxs-lookup"><span data-stu-id="dc98f-123">Values (optional)</span></span>\
<span data-ttu-id="dc98f-124">Коллекция элементов, по которой выполняется проход.</span><span class="sxs-lookup"><span data-stu-id="dc98f-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="dc98f-125">Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dc98f-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>

<span data-ttu-id="dc98f-126">Комплетионкондитион (необязательно) </span><span class="sxs-lookup"><span data-stu-id="dc98f-126">CompletionCondition (optional)</span></span>\
<span data-ttu-id="dc98f-127">Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="dc98f-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="dc98f-128">Если результат оценки равен `true`, то запланированные ожидающие итерации отменяются.</span><span class="sxs-lookup"><span data-stu-id="dc98f-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="dc98f-129">Если это свойство не задано, все действия в коллекции ветвей выполняются до завершения.</span><span class="sxs-lookup"><span data-stu-id="dc98f-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>

## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="dc98f-130">Пример использования ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="dc98f-130">Example of using ParallelForEach</span></span>

<span data-ttu-id="dc98f-131">В следующем коде демонстрируется использование в приложении действия ParallelForEach.</span><span class="sxs-lookup"><span data-stu-id="dc98f-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>

```csharp
string[] names = { "bill", "steve", "ray" };

DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };

Activity sampleUsage =
    new ParallelForEach
    {
       Values = new InArgument<IEnumerable>(c=> names),
       Body = new ActivityAction<object>
       {
           Argument = iterationVariable,
           Handler = new WriteLine
           {
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))
           }
       }
   };
```

## <a name="parallelforeach-designer"></a><span data-ttu-id="dc98f-132">Конструктор ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="dc98f-132">ParallelForEach designer</span></span>

<span data-ttu-id="dc98f-133">Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="dc98f-134">Конструктор появится в области элементов в категории **примеры**, **неуниверсальные действия** .</span><span class="sxs-lookup"><span data-stu-id="dc98f-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="dc98f-135">Конструктор называется **параллелфореачвисбодифактори** на панели элементов, так как действие предоставляет <xref:System.Activities.Presentation.IActivityTemplateFactory> на панели элементов, который создает действие с правильно настроенным <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="dc98f-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>

```csharp
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory
{
    public Activity Create(DependencyObject target)
    {
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()
        {
            Body = new ActivityAction<object>()
            {
                Argument = new DelegateInArgument<object>()
                {
                    Name = "item"
                }
            }
        };
    }
}
```

## <a name="to-run-the-sample"></a><span data-ttu-id="dc98f-136">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="dc98f-136">To run the sample</span></span>

1. <span data-ttu-id="dc98f-137">Установите выбранный проект в качестве проекта для запуска решения.</span><span class="sxs-lookup"><span data-stu-id="dc98f-137">Set the project of your choice as the startup project of the solution.</span></span>

    1. <span data-ttu-id="dc98f-138">**Кодетестклиент** показывает, как использовать действие с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="dc98f-138">**CodeTestClient** shows how to use the activity using code.</span></span>

    2. <span data-ttu-id="dc98f-139">**Десигнертестклиент** показывает, как использовать действие в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="dc98f-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>

2. <span data-ttu-id="dc98f-140">Постройте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="dc98f-140">Build and run the project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc98f-141">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc98f-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc98f-142">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dc98f-142">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="dc98f-143">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="dc98f-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc98f-144">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="dc98f-144">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
