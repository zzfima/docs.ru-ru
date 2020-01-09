---
title: Неуниверсальное действие ForEach
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 93a6b1d815ef6478974ceadf8ad935be2a3bdea5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338657"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="a9632-102">Неуниверсальное действие ForEach</span><span class="sxs-lookup"><span data-stu-id="a9632-102">Non-Generic ForEach</span></span>
<span data-ttu-id="a9632-103">В область элементов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] входит набор действий потока управления, включая элемент <xref:System.Activities.Statements.ForEach%601>, который позволяет проходить по коллекциям <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a9632-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="a9632-104">Свойство <xref:System.Activities.Statements.ForEach%601> элемента <xref:System.Activities.Statements.ForEach%601.Values%2A> должно иметь тип <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a9632-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a9632-105">Это запрещает пользователям проходить по структурам данных, в которых реализован интерфейс <xref:System.Collections.Generic.IEnumerable%601> (например, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="a9632-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="a9632-106">Неуниверсальная версия <xref:System.Activities.Statements.ForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a9632-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="a9632-107">В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ForEach%601> и конструктор для него.</span><span class="sxs-lookup"><span data-stu-id="a9632-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="a9632-108">Это действие позволяет проходить по <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="a9632-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="a9632-109">Действие ForEach</span><span class="sxs-lookup"><span data-stu-id="a9632-109">ForEach Activity</span></span>  
 <span data-ttu-id="a9632-110">Инструкция C#/Visual Basic `foreach` перечисляет элементы коллекции, выполняя внедренный оператор для каждого элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="a9632-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="a9632-111">Действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)], эквивалентными `foreach`, являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="a9632-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="a9632-112">Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое.</span><span class="sxs-lookup"><span data-stu-id="a9632-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="a9632-113">Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.</span><span class="sxs-lookup"><span data-stu-id="a9632-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="a9632-114">Для большинства случаев универсальная версия действия является предпочтительной, поскольку она охватывает большинство сценариев, в которых будет использоваться действие, и предоставляет возможность проверки соответствия типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a9632-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="a9632-115">Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="a9632-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="a9632-116">Определение класса</span><span class="sxs-lookup"><span data-stu-id="a9632-116">Class Definition</span></span>  
 <span data-ttu-id="a9632-117">В следующем примере кода показано определение неуниверсального действия `ForEach`.</span><span class="sxs-lookup"><span data-stu-id="a9632-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```csharp  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="a9632-118">Содержание (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a9632-118">Body (optional)</span></span>  
 <span data-ttu-id="a9632-119">Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a9632-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="a9632-120">Каждый отдельный элемент передается в текст через свойство `Argument`.</span><span class="sxs-lookup"><span data-stu-id="a9632-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="a9632-121">Значения (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a9632-121">Values (optional)</span></span>  
 <span data-ttu-id="a9632-122">Коллекция элементов, по которой выполняется проход.</span><span class="sxs-lookup"><span data-stu-id="a9632-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="a9632-123">Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9632-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="a9632-124">Пример использования ForEach</span><span class="sxs-lookup"><span data-stu-id="a9632-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="a9632-125">В следующем кода демонстрируется использование в приложении действия ForEach.</span><span class="sxs-lookup"><span data-stu-id="a9632-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```csharp  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
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
  
|<span data-ttu-id="a9632-126">Условие</span><span class="sxs-lookup"><span data-stu-id="a9632-126">Condition</span></span>|<span data-ttu-id="a9632-127">Message</span><span class="sxs-lookup"><span data-stu-id="a9632-127">Message</span></span>|<span data-ttu-id="a9632-128">Серьезность</span><span class="sxs-lookup"><span data-stu-id="a9632-128">Severity</span></span>|<span data-ttu-id="a9632-129">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="a9632-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="a9632-130">Значением является `null`</span><span class="sxs-lookup"><span data-stu-id="a9632-130">Values is `null`</span></span>|<span data-ttu-id="a9632-131">Не указано значение необходимого аргумента действия "Values".</span><span class="sxs-lookup"><span data-stu-id="a9632-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="a9632-132">Ошибка .</span><span class="sxs-lookup"><span data-stu-id="a9632-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="a9632-133">Конструктор ForEach</span><span class="sxs-lookup"><span data-stu-id="a9632-133">ForEach Designer</span></span>  
 <span data-ttu-id="a9632-134">Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="a9632-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="a9632-135">Конструктор появится в области элементов в категории **примеры**, **неуниверсальные действия** .</span><span class="sxs-lookup"><span data-stu-id="a9632-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="a9632-136">Конструктор называется **фореачвисбодифактори** на панели элементов, так как действие предоставляет <xref:System.Activities.Presentation.IActivityTemplateFactory> на панели элементов, что создает действие с правильно настроенным <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="a9632-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```csharp  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="a9632-137">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="a9632-137">To run this sample</span></span>  
  
1. <span data-ttu-id="a9632-138">Установите выбранный проект в качестве проекта для запуска решения.</span><span class="sxs-lookup"><span data-stu-id="a9632-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1. <span data-ttu-id="a9632-139">**Кодетестклиент** показывает, как использовать действие с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="a9632-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2. <span data-ttu-id="a9632-140">**Десигнертестклиент** показывает, как использовать действие в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="a9632-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2. <span data-ttu-id="a9632-141">Постройте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="a9632-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9632-142">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a9632-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9632-143">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a9632-143">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a9632-144">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="a9632-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9632-145">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a9632-145">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
