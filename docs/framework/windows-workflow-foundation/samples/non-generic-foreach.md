---
title: "Неуниверсальное действие ForEach | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Неуниверсальное действие ForEach
В область элементов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] входит набор действий потока управления, включая элемент <xref:System.Activities.Statements.ForEach%601>, который позволяет проходить по коллекциям <xref:System.Collections.IEnumerable%601>.  
  
 Свойство <xref:System.Activities.Statements.ForEach%601> элемента <xref:System.Activities.Statements.ForEach%601.Values%2A> должно иметь тип <xref:System.Collections.IEnumerable%601>.  Это запрещает пользователям проходить по структурам данных, в которых реализован интерфейс <xref:System.Collections.IEnumerable%601> \(например, <xref:System.Collections.ArrayList>\).  Неуниверсальная версия <xref:System.Activities.Statements.ForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.  
  
 В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ForEach%601> и конструктор для него.  Это действие позволяет проходить по <xref:System.Collections.ArrayList>.  
  
## Действие ForEach  
 Оператор `foreach` в C\# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции.  Действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)], эквивалентными `foreach`, являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>.  Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое.  Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.  
  
 Для большинства случаев универсальная версия действия является предпочтительной, поскольку она охватывает большинство сценариев, в которых будет использоваться действие, и предоставляет возможность проверки соответствия типов во время компиляции.  Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.  
  
## Определение класса  
 В следующем примере кода показано определение неуниверсального действия `ForEach`.  
  
```  
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
  
 Содержание \(необязательно\)  
 Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции.  Каждый отдельный элемент передается в текст через свойство `Argument`.  
  
 Значения \(необязательно\)  
 Коллекция элементов, по которой выполняется проход.  Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.  
  
## Пример использования ForEach  
 В следующем кода демонстрируется использование в приложении действия ForEach.  
  
```  
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
  
|Условие|Сообщение|Важность|Тип исключения|  
|-------------|---------------|--------------|--------------------|  
|Значением является `null`|Не указано значение необходимого аргумента действия "Values".|Ошибка|<xref:System.InvalidOperationException>|  
  
## Конструктор ForEach  
 Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ForEach%601>.  Конструктор выводится в области элементов **Образцы**, категория **Неуниверсальные действия**.  Конструктор на панели инструментов называется **ForEachWithBodyFactory**, поскольку действие предоставляет на панели инструментов объект <xref:System.Activities.Presentation.IActivityTemplateFactory>, который создает действие со свойством, настроенным как <xref:System.Activities.ActivityAction>.  
  
```  
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
  
#### Запуск образца  
  
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
>  `<ДискУстановки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`