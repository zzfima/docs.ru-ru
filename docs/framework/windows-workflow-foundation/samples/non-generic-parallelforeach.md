---
title: "Нестандартное действие ParallelForEach | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Нестандартное действие ParallelForEach
В область элементов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] входит набор действий потока управления, включая элемент <xref:System.Activities.Statements.ParallelForEach%601>, который позволяет проходить по коллекциям <xref:System.Collections.IEnumerable%601>.  
  
 Свойство <xref:System.Activities.Statements.ParallelForEach%601> элемента <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> должно иметь тип <xref:System.Collections.IEnumerable%601>.  Это запрещает пользователям проходить по структурам данных, в которых реализован интерфейс <xref:System.Collections.IEnumerable%601> \(например, <xref:System.Collections.ArrayList>\).  Неуниверсальная версия <xref:System.Activities.Statements.ParallelForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.  
  
 В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ParallelForEach%601> и конструктор для него.  Это действие позволяет проходить по <xref:System.Collections.ArrayList>.  
  
## Действие ParallelForEach  
 Оператор `foreach` в C\# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции.  Эквивалентными действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>.  Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое.  Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> имеет <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, поэтому действие <xref:System.Activities.Statements.ParallelForEach%601> может завершиться рано, если оценка <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вернет результат `true`.  Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.  
  
 Для большинства случаев универсальная версия действия является предпочтительным вариантом, поскольку он охватывает большинство сценариев, в которых используется действие, и предоставляет проверку соответствия типов во время компиляции.  Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.  
  
## Определение класса  
 В следующем примере кода показано определение неуниверсального действия `ParallelForEach`.  
  
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
  
 Содержание \(необязательно\)  
 Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции.  Каждый отдельный элемент передается в текст через свойство Argument.  
  
 Значения \(необязательно\)  
 Коллекция элементов, по которой выполняется проход.  Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.  
  
 CompletionCondition \(по выбору\)  
 Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.  Если результат оценки равен `true`, то запланированные ожидающие итерации отменяются.  Если это свойство не задано, все действия в коллекции ветвей выполняются до завершения.  
  
## Пример использования ParallelForEach  
 В следующем коде демонстрируется использование в приложении действия ParallelForEach.  
  
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
  
## Конструктор ParallelForEach  
 Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ParallelForEach%601>.  Конструктор выводится в области элементов **Образцы**, категория **Неуниверсальные действия**.  Конструктор на панели инструментов называется **ParallelForEachWithBodyFactory**, поскольку это действие предоставляет на панели инструментов объект <xref:System.Activities.Presentation.IActivityTemplateFactory> с настроенным действием <xref:System.Activities.ActivityAction>.  
  
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
  
#### Выполнение образца  
  
1.  Установите выбранный проект в качестве проекта для запуска решения.  
  
    1.  В образце **CodeTestClient** показано использование действия в коде.  
  
    2.  В образце **DesignerTestClient** показано использование действия в конструкторе.  
  
2.  Постройте и запустите проект.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<ДискУстановки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`