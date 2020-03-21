---
title: Неуниверсальное действие ForEach
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 08dbac3974915f823a4f6e39f35927453a7c4b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142710"
---
# <a name="non-generic-foreach"></a>Неуниверсальное действие ForEach
В область элементов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] входит набор действий потока управления, включая элемент <xref:System.Activities.Statements.ForEach%601>, который позволяет проходить по коллекциям <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Свойство <xref:System.Activities.Statements.ForEach%601> элемента <xref:System.Activities.Statements.ForEach%601.Values%2A> должно иметь тип <xref:System.Collections.Generic.IEnumerable%601>. Это запрещает пользователям проходить по структурам данных, в которых реализован интерфейс <xref:System.Collections.Generic.IEnumerable%601> (например, <xref:System.Collections.ArrayList>). Неуниверсальная версия <xref:System.Activities.Statements.ForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.  
  
 В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ForEach%601> и конструктор для него. Это действие позволяет проходить по <xref:System.Collections.ArrayList>.  
  
## <a name="foreach-activity"></a>Действие ForEach  
 В отчете C/Visual Basic `foreach` перечислены элементы коллекции, исправления встроенного оператора для каждого элемента коллекции. Действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)], эквивалентными `foreach`, являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>. Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое. Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.  
  
 Для большинства случаев универсальная версия действия является предпочтительной, поскольку она охватывает большинство сценариев, в которых будет использоваться действие, и предоставляет возможность проверки соответствия типов во время компиляции. Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.  
  
## <a name="class-definition"></a>Определение класса  
 В следующем примере кода показано определение неуниверсального действия `ForEach`.  
  
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
  
 Содержание (необязательно)  
 Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции. Каждый отдельный элемент передается в текст через свойство `Argument`.  
  
 Значения (необязательно)  
 Коллекция элементов, по которой выполняется проход. Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.  
  
## <a name="example-of-using-foreach"></a>Пример использования ForEach  
 В следующем кода демонстрируется использование в приложении действия ForEach.  
  
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
  
|Условие|Сообщение|Severity|Тип исключения|  
|---------------|-------------|--------------|--------------------|  
|Значением является `null`|Не указано значение необходимого аргумента действия "Values".|Error|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>Конструктор ForEach  
 Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ForEach%601>. Дизайнер появляется в наборе инструментов в категории **«Образцы»,** **несвязанные действия.** Дизайнер называется **ForEachWithBodyFactory** в наборе инструментов, <xref:System.Activities.Presentation.IActivityTemplateFactory> потому что действие подвергает в наборе <xref:System.Activities.ActivityAction>инструментов, который создает деятельность с правильно настроенной.  
  
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
  
#### <a name="to-run-this-sample"></a>Запуск образца  
  
1. Установите выбранный проект в качестве проекта для запуска решения.  
  
    1. **CodeTestClient** показывает, как использовать действие с помощью кода.  
  
    2. **DesignerTestClient** показывает, как использовать деятельность в рамках дизайнера.  
  
2. Постройте и запустите проект.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
