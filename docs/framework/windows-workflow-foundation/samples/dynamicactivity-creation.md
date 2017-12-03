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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43f39d5c78e59925ad73fe7277300848877f83f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="dynamicactivity-creation"></a>Создание действия DynamicActivity
В этом образце показываются два разных способа создания действия во время выполнения с помощью действия <xref:System.Activities.DynamicActivity>.  
  
 В этом образце во время выполнения создается действие с текстом, содержащим действие <xref:System.Activities.Statements.Sequence>, которое содержит действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.Assign%601>. Входной список целых чисел передается действию и задается в виде свойства. Затем действие <xref:System.Activities.Statements.ForEach%601> проходит по списку значений и аккумулирует его. Среднее значение в действии <xref:System.Activities.Statements.Assign%601> вычисляется методом деления аккумулятора на количество элементов в списке, после чего оно задается как среднее.  
  
 Образец демонстрирует использование действия <xref:System.Activities.DynamicActivity>, которое передает переменные в качестве входящих аргументов и возвращает значения в качестве выходных аргументов. Действие имеет один входной аргумент с именем `Numbers`, являющийся списком целых чисел. Действие <xref:System.Activities.Statements.ForEach%601> проходит по списку значений и аккумулирует его. Среднее значение в действии <xref:System.Activities.Statements.Assign%601> вычисляется методом деления аккумулятора на количество элементов в списке и задания полученного значения в качестве среднего. Среднее значение возвращается в виде выходного аргумент с именем `Average`.  
  
 Если динамическое действие создается программным образом, входные и выходные значения объявляются так, как это показано в следующем примере кода.  
  
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
  
 В следующем примере кода показано полное определение `DynamicActivity`, вычисляющего среднее значение из значений в списке.  
  
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
  
 Созданные на языке XAML входное и выходное значения объявляются так, как это показано в следующем примере.  
  
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
  
 XAML можно создать визуально с помощью [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]. Если он включен в проект Visual Studio, не забудьте задать его «действие сборки» на «Нет» для предотвращения компилируемого. Затем XAML можно загружать динамически с помощью следующего вызова.  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 Экземпляр <xref:System.Activities.DynamicActivity>, созданный программным образом или методом загрузки рабочего процесса XAML, можно использовать так, как это показано в следующем примере кода. Обратите внимание, что «act», передаваемая `WorkflowInvoker.Invoke` это команда «act» <xref:System.Activities.Activity> определено в первом примере кода.  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения DynamicActivityCreation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
## <a name="command-line-arguments"></a>Аргументы командной строки  
 Этот образец принимает аргументы командной строки. Пользователи могут предоставить действию список чисел для вычисления их среднего значения. Используемый список чисел передается как список чисел, разделенных пробелами. Например, чтобы вычислить среднее значение чисел 5, 10 и 32, образец следует вызвать с использованием следующей командной строки.  
  
 **DynamicActivityCreation 5 10 32**  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`