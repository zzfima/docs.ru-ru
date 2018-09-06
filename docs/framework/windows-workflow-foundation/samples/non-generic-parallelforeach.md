---
title: Нестандартное действие ParallelForEach
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 70d5de587dda3cb61205a8d77f2173df9b93498b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881815"
---
# <a name="non-generic-parallelforeach"></a>Нестандартное действие ParallelForEach
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] в область элементов поставляется набор действий потока управления, включая <xref:System.Activities.Statements.ParallelForEach%601>, который позволяет проходить по <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` коллекций.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> требуется его <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> свойство типа <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. Это запрещает пользователям проходить по структурам данных, которые реализуют <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` интерфейса (например, <xref:System.Collections.ArrayList>). Неуниверсальная версия <xref:System.Activities.Statements.ParallelForEach%601> выполняет это требование за счет большей гибкости во время выполнения, чтобы обеспечить совместимость типов значений в коллекции.  
  
 В этом образце показано, как реализовать неуниверсальное действие <xref:System.Activities.Statements.ParallelForEach%601> и конструктор для него. Это действие позволяет проходить по <xref:System.Collections.ArrayList>.  
  
## <a name="parallelforeach-activity"></a>Действие ParallelForEach  
 Оператор `foreach` в C# и Visual Basic перечисляет элементы коллекции, выполняя внедренные в цикле операторы для каждого элемента в коллекции. Эквивалентными действиями [!INCLUDE[wf1](../../../../includes/wf1-md.md)] являются действия <xref:System.Activities.Statements.ForEach%601> и <xref:System.Activities.Statements.ParallelForEach%601>. Действие <xref:System.Activities.Statements.ForEach%601> содержит список значений и содержимое. Во время выполнения действие проходит по списку, и текст действия выполняется для каждого значения в списке.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> имеет <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, поэтому действие <xref:System.Activities.Statements.ParallelForEach%601> может завершиться рано, если оценка <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вернет результат `true`. Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации.  
  
 Для большинства случаев универсальная версия действия является предпочтительным вариантом, поскольку он охватывает большинство сценариев, в которых используется действие, и предоставляет проверку соответствия типов во время компиляции. Неуниверсальная версия позволяет проходить по типам, где реализован неуниверсальный интерфейс <xref:System.Collections.IEnumerable>.  
  
## <a name="class-definition"></a>Определение класса  
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
  
 Содержание (необязательно)  
 Действие <xref:System.Activities.ActivityAction> типа <xref:System.Object>, которое выполняется для каждого элемента в коллекции. Каждый отдельный элемент передается в текст через свойство Argument.  
  
 Значения (необязательно)  
 Коллекция элементов, по которой выполняется проход. Проверка совместимости типов для всех элементов коллекции проводится во время выполнения.  
  
 CompletionCondition (по выбору)  
 Свойство <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> вычисляется после завершения каждой итерации. Если результат оценки равен `true`, то запланированные ожидающие итерации отменяются. Если это свойство не задано, все действия в коллекции ветвей выполняются до завершения.  
  
## <a name="example-of-using-parallelforeach"></a>Пример использования ParallelForEach  
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
  
## <a name="parallelforeach-designer"></a>Конструктор ParallelForEach  
 Конструктор действий для образца аналогичен конструктору, предоставляемому для встроенного действия <xref:System.Activities.Statements.ParallelForEach%601>. Конструктор отображается в области элементов в **примеры**, **неуниверсальные действия** категории. Конструктор называется **ParallelForEachWithBodyFactory** на панели элементов, поскольку это действие предоставляет <xref:System.Activities.Presentation.IActivityTemplateFactory> в области элементов, который создает действие с настроенным <xref:System.Activities.ActivityAction>.  
  
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
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Установите выбранный проект в качестве проекта для запуска решения.  
  
    1.  **CodeTestClient** показано, как с помощью действия, с помощью кода.  
  
    2.  **DesignerTestClient** показано, как с помощью действия в конструкторе.  
  
2.  Постройте и запустите проект.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
