---
title: "Неуниверсальное действие ForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 234e5a7ef9591c1e943484402bc235b62ad7fb87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="non-generic-foreach"></a>Неуниверсальное действие ForEach
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]поставляется в область элементов набор действий потока управления, включая <xref:System.Activities.Statements.ForEach%601>, который позволяет проходить по <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` коллекций.  
  
 <xref:System.Activities.Statements.ForEach%601>требуется его <xref:System.Activities.Statements.ForEach%601.Values%2A> свойство с типом <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. Это запрещает пользователям проходить по структурам данных, которые реализуют <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` интерфейса (например, <xref:System.Collections.ArrayList>). Неуниверсальная версия <xref:System.Activities.Statements.ForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.  
  
 В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ForEach%601> и конструктор для него. Это действие позволяет проходить по <xref:System.Collections.ArrayList>.  
  
## <a name="foreach-activity"></a>Действие ForEach  
 Оператор `foreach` в C# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции. Действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)], эквивалентными `foreach`, являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>. Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое. Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.  
  
 Для большинства случаев универсальная версия действия является предпочтительной, поскольку она охватывает большинство сценариев, в которых будет использоваться действие, и предоставляет возможность проверки соответствия типов во время компиляции. Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.  
  
## <a name="class-definition"></a>Определение класса  
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
  
 Содержание (необязательно)  
 Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции. Каждый отдельный элемент передается в текст через свойство `Argument`.  
  
 Значения (необязательно)  
 Коллекция элементов, по которой выполняется проход. Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.  
  
## <a name="example-of-using-foreach"></a>Пример использования ForEach  
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
|---------------|-------------|--------------|--------------------|  
|Значением является `null`|Не указано значение необходимого аргумента действия "Values".|Ошибка|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>Конструктор ForEach  
 Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ForEach%601>. Откроется конструктор на панели инструментов в **образцы**, **неуниверсальные действия** категории. Конструктор называется **ForEachWithBodyFactory** в панели элементов, поскольку это действие предоставляет <xref:System.Activities.Presentation.IActivityTemplateFactory> на панели инструментов, который создает действие с правильно настроенной <xref:System.Activities.ActivityAction>.  
  
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
  
#### <a name="to-run-this-sample"></a>Запуск образца  
  
1.  Установите выбранный проект в качестве проекта для запуска решения.  
  
    1.  **CodeTestClient** показано использование действия в коде.  
  
    2.  **DesignerTestClient** показано, как использовать действие в конструкторе.  
  
2.  Постройте и запустите проект.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
