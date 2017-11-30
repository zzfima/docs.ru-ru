---
title: "Создание действия DynamicActivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02dc1dfda28aae15889c0239f2913a8240869a76
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="3cb0b-102">Создание действия DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="3cb0b-102">DynamicActivity Creation</span></span>
<span data-ttu-id="3cb0b-103">В этом образце показываются два разных способа создания действия во время выполнения с помощью действия <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="3cb0b-104">В этом образце во время выполнения создается действие с текстом, содержащим действие <xref:System.Activities.Statements.Sequence>, которое содержит действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.Assign%601>.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="3cb0b-105">Входной список целых чисел передается действию и задается в виде свойства.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="3cb0b-106">Затем действие <xref:System.Activities.Statements.ForEach%601> проходит по списку значений и аккумулирует его.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="3cb0b-107">Среднее значение в действии <xref:System.Activities.Statements.Assign%601> вычисляется методом деления аккумулятора на количество элементов в списке, после чего оно задается как среднее.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="3cb0b-108">Образец демонстрирует использование действия <xref:System.Activities.DynamicActivity>, которое передает переменные в качестве входящих аргументов и возвращает значения в качестве выходных аргументов.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="3cb0b-109">Действие имеет один входной аргумент с именем `Numbers`, являющийся списком целых чисел.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="3cb0b-110">Действие <xref:System.Activities.Statements.ForEach%601> проходит по списку значений и аккумулирует его.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="3cb0b-111">Среднее значение в действии <xref:System.Activities.Statements.Assign%601> вычисляется методом деления аккумулятора на количество элементов в списке и задания полученного значения в качестве среднего.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="3cb0b-112">Среднее значение возвращается в виде выходного аргумент с именем `Average`.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="3cb0b-113">Если динамическое действие создается программным образом, входные и выходные значения объявляются так, как это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 <span data-ttu-id="3cb0b-114">В следующем примере кода показано полное определение `DynamicActivity`, вычисляющего среднее значение из значений в списке.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 <span data-ttu-id="3cb0b-115">Созданные на языке XAML входное и выходное значения объявляются так, как это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 <span data-ttu-id="3cb0b-116">XAML можно создать визуально с помощью [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb0b-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="3cb0b-117">Если он включен в проект Visual Studio, не забудьте задать его «действие сборки» на «Нет» для предотвращения компилируемого.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="3cb0b-118">Затем XAML можно загружать динамически с помощью следующего вызова.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="3cb0b-119">Экземпляр <xref:System.Activities.DynamicActivity>, созданный программным образом или методом загрузки рабочего процесса XAML, можно использовать так, как это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="3cb0b-120">Обратите внимание, что «act», передаваемая `WorkflowInvoker.Invoke` это команда «act» <xref:System.Activities.Activity> определено в первом примере кода.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3cb0b-121">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="3cb0b-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="3cb0b-122">Откройте файл решения DynamicActivityCreation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb0b-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="3cb0b-123">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3cb0b-124">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="3cb0b-125">Аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="3cb0b-125">Command line arguments</span></span>  
 <span data-ttu-id="3cb0b-126">Этот образец принимает аргументы командной строки.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="3cb0b-127">Пользователи могут предоставить действию список чисел для вычисления их среднего значения.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="3cb0b-128">Используемый список чисел передается как список чисел, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="3cb0b-129">Например, чтобы вычислить среднее значение чисел 5, 10 и 32, образец следует вызвать с использованием следующей командной строки.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="3cb0b-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="3cb0b-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="3cb0b-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3cb0b-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3cb0b-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3cb0b-133">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cb0b-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3cb0b-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3cb0b-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`