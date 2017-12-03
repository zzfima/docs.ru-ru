---
title: "Нестандартное действие ParallelForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c8c02c920eda881f4a08925e3bff0567244e5c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="71c7f-102">Нестандартное действие ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="71c7f-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="71c7f-103">поставляется в область элементов набор действий потока управления, включая <xref:System.Activities.Statements.ParallelForEach%601>, который позволяет проходить по <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` коллекций.</span><span class="sxs-lookup"><span data-stu-id="71c7f-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="71c7f-104"><xref:System.Activities.Statements.ParallelForEach%601>требуется его <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> свойство с типом <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="71c7f-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="71c7f-105">Это запрещает пользователям проходить по структурам данных, которые реализуют <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` интерфейса (например, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="71c7f-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="71c7f-106">Неуниверсальная версия <xref:System.Activities.Statements.ParallelForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.</span><span class="sxs-lookup"><span data-stu-id="71c7f-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="71c7f-107">В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ParallelForEach%601> и конструктор для него.</span><span class="sxs-lookup"><span data-stu-id="71c7f-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="71c7f-108">Это действие позволяет проходить по <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="71c7f-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="71c7f-109">Действие ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="71c7f-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="71c7f-110">Оператор `foreach` в C# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="71c7f-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="71c7f-111">Эквивалентными действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="71c7f-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="71c7f-112">Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое.</span><span class="sxs-lookup"><span data-stu-id="71c7f-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="71c7f-113">Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.</span><span class="sxs-lookup"><span data-stu-id="71c7f-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="71c7f-114"><xref:System.Activities.Statements.ParallelForEach%601> имеет <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, поэтому действие <xref:System.Activities.Statements.ParallelForEach%601> может завершиться рано, если оценка <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вернет результат `true`.</span><span class="sxs-lookup"><span data-stu-id="71c7f-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="71c7f-115">Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="71c7f-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="71c7f-116">Для большинства случаев универсальная версия действия является предпочтительным вариантом, поскольку он охватывает большинство сценариев, в которых используется действие, и предоставляет проверку соответствия типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="71c7f-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="71c7f-117">Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="71c7f-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="71c7f-118">Определение класса</span><span class="sxs-lookup"><span data-stu-id="71c7f-118">Class Definition</span></span>  
 <span data-ttu-id="71c7f-119">В следующем примере кода показано определение неуниверсального действия `ParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="71c7f-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
```  
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
  
 <span data-ttu-id="71c7f-120">Содержание (необязательно)</span><span class="sxs-lookup"><span data-stu-id="71c7f-120">Body (optional)</span></span>  
 <span data-ttu-id="71c7f-121">Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="71c7f-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="71c7f-122">Каждый отдельный элемент передается в текст через свойство Argument.</span><span class="sxs-lookup"><span data-stu-id="71c7f-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="71c7f-123">Значения (необязательно)</span><span class="sxs-lookup"><span data-stu-id="71c7f-123">Values (optional)</span></span>  
 <span data-ttu-id="71c7f-124">Коллекция элементов, по которой выполняется проход.</span><span class="sxs-lookup"><span data-stu-id="71c7f-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="71c7f-125">Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="71c7f-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="71c7f-126">CompletionCondition (по выбору)</span><span class="sxs-lookup"><span data-stu-id="71c7f-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="71c7f-127">Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="71c7f-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="71c7f-128">Если результат оценки равен `true`, то запланированные ожидающие итерации отменяются.</span><span class="sxs-lookup"><span data-stu-id="71c7f-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="71c7f-129">Если это свойство не задано, все действия в коллекции ветвей выполняются до завершения.</span><span class="sxs-lookup"><span data-stu-id="71c7f-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="71c7f-130">Пример использования ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="71c7f-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="71c7f-131">В следующем коде демонстрируется использование в приложении действия ParallelForEach.</span><span class="sxs-lookup"><span data-stu-id="71c7f-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
```  
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
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="71c7f-132">Конструктор ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="71c7f-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="71c7f-133">Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="71c7f-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="71c7f-134">Откроется конструктор на панели инструментов в **образцы**, **неуниверсальные действия** категории.</span><span class="sxs-lookup"><span data-stu-id="71c7f-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="71c7f-135">Конструктор называется **ParallelForEachWithBodyFactory** в панели элементов, поскольку это действие предоставляет <xref:System.Activities.Presentation.IActivityTemplateFactory> на панели инструментов, который создает действие с правильно настроенной <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="71c7f-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
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
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="71c7f-136">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="71c7f-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="71c7f-137">Установите выбранный проект в качестве проекта для запуска решения.</span><span class="sxs-lookup"><span data-stu-id="71c7f-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="71c7f-138">**CodeTestClient** показано использование действия в коде.</span><span class="sxs-lookup"><span data-stu-id="71c7f-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="71c7f-139">**DesignerTestClient** показано, как использовать действие в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="71c7f-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="71c7f-140">Постройте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="71c7f-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="71c7f-141">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="71c7f-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="71c7f-142">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="71c7f-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="71c7f-143">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71c7f-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="71c7f-144">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="71c7f-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
