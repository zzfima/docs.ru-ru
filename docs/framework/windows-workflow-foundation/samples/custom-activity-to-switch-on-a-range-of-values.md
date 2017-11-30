---
title: "Настраиваемое действие для переключения в диапазоне значений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f2f422c4001c2e6ec46fc796e8dbf1b85e6a2b77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="946ff-102">Настраиваемое действие для переключения в диапазоне значений</span><span class="sxs-lookup"><span data-stu-id="946ff-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="946ff-103">В этом образце демонстрируется создание настраиваемого действия, которое расширяет использование <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="946ff-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="946ff-104">Обычная инструкция <xref:System.Activities.Statements.Switch%601> позволяет выполнять переключение на основании одного значения.</span><span class="sxs-lookup"><span data-stu-id="946ff-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="946ff-105">Но существуют бизнес-сценарии, в которых действие должно переключаться в зависимости от диапазона значений.</span><span class="sxs-lookup"><span data-stu-id="946ff-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="946ff-106">Например, действие может выполнять одну операцию, если значение, по которому производится переключение, находится в диапазоне от 1 до 5, и другую операцию, если значение находится в диапазоне от 6 до 10, а также операцию по умолчанию для всех прочих значений.</span><span class="sxs-lookup"><span data-stu-id="946ff-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="946ff-107">Это настраиваемое действие выполняет именно такую задачу.</span><span class="sxs-lookup"><span data-stu-id="946ff-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="946ff-108">Действие SwitchRange</span><span class="sxs-lookup"><span data-stu-id="946ff-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="946ff-109">Действие `SwitchRange` планирует дочернее действие, если значение результата его выражения входит в диапазон одного из его `Cases`.</span><span class="sxs-lookup"><span data-stu-id="946ff-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="946ff-110">В следующем примере кода показано настраиваемое действие, которое переключается в зависимости от диапазона значений.</span><span class="sxs-lookup"><span data-stu-id="946ff-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="946ff-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="946ff-111">Property</span></span>|<span data-ttu-id="946ff-112">Описание</span><span class="sxs-lookup"><span data-stu-id="946ff-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="946ff-113">Выражение</span><span class="sxs-lookup"><span data-stu-id="946ff-113">Expression</span></span>|<span data-ttu-id="946ff-114">Здесь представлено выражение, которое вычисляется и сравнивается с диапазонами в списке вариантов.</span><span class="sxs-lookup"><span data-stu-id="946ff-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="946ff-115">Результат выражения имеет тип T.</span><span class="sxs-lookup"><span data-stu-id="946ff-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="946ff-116">Cases</span><span class="sxs-lookup"><span data-stu-id="946ff-116">Cases</span></span>|<span data-ttu-id="946ff-117">Каждый вариант состоит из диапазона (From - от и To - до) и операции (Body - тело).</span><span class="sxs-lookup"><span data-stu-id="946ff-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="946ff-118">Выражение вычисляется и сравнивается с диапазоном значений.</span><span class="sxs-lookup"><span data-stu-id="946ff-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="946ff-119">Если результат выражения входит в диапазон одного из вариантов, выполняется соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="946ff-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="946ff-120">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="946ff-120">Default</span></span>|<span data-ttu-id="946ff-121">Действие, выполняемое в случае, если значение не соответствует ни одному варианту.</span><span class="sxs-lookup"><span data-stu-id="946ff-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="946ff-122">При установке значения `null` не выполняется ни одно действие.</span><span class="sxs-lookup"><span data-stu-id="946ff-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="946ff-123">Класс CaseRange</span><span class="sxs-lookup"><span data-stu-id="946ff-123">CaseRange Class</span></span>  
 <span data-ttu-id="946ff-124">Класс `CaseRange` представляет диапазон для действия в `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="946ff-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="946ff-125">Каждый экземпляр класса `CaseRange` содержит диапазон (включающий границы `From` и `To`) и элемент `Body` действия, которое планируется для выполнения, если вычисленное выражение в классе `SwitchRange` попадает в диапазон.</span><span class="sxs-lookup"><span data-stu-id="946ff-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="946ff-126">Следующий пример кода является определением для класса `CaseRange`.</span><span class="sxs-lookup"><span data-stu-id="946ff-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="946ff-127">И класс `SwitchRange`, и класс `CaseRange`, определенные в образце, являются универсальными классами, которые могут работать с любым типом, реализующим интерфейс `IComparable` аналогично классу <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="946ff-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="946ff-128">Использование примера</span><span class="sxs-lookup"><span data-stu-id="946ff-128">Sample Usage</span></span>  
 <span data-ttu-id="946ff-129">В следующем примере кода показано, как использовать действие `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="946ff-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="946ff-130">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="946ff-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="946ff-131">С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения SwitchRange.sln.</span><span class="sxs-lookup"><span data-stu-id="946ff-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="946ff-132">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="946ff-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="946ff-133">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="946ff-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="946ff-134">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="946ff-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="946ff-135">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="946ff-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="946ff-136">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="946ff-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="946ff-137">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="946ff-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`  
  
## <a name="see-also"></a><span data-ttu-id="946ff-138">См. также</span><span class="sxs-lookup"><span data-stu-id="946ff-138">See Also</span></span>
