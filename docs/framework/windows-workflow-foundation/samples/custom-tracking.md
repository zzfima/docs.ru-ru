---
title: Настраиваемое отслеживание
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71eb3adaae6a474cf4e0766029c549dfe3a08383
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="custom-tracking"></a>Настраиваемое отслеживание
В данном образце демонстрируется создание настраиваемого участника отслеживания и запись содержимого данных отслеживания в консоль. Помимо этого, в образце демонстрируется создание <xref:System.Activities.Tracking.CustomTrackingRecord> объектов, заполненных определенными пользователем данными. Консольный участник отслеживания фильтрует <xref:System.Activities.Tracking.TrackingRecord> объекты, выпущенные рабочим процессом, используя объект профиля отслеживания, созданный в коде.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Windows Workflow Foundation (WF) предоставляет инфраструктуру для отслеживания выполнения экземпляра рабочего процесса. Среда выполнения для отслеживания реализует экземпляр рабочего процесса для создания событий, связанных с жизненным циклом рабочего процесса, действиями рабочего процесса и настраиваемыми событиями отслеживания. В следующих сведениях о таблице подробно описаны основные компоненты инфраструктуры отслеживания.  
  
|Компонент|Описание|  
|---------------|-----------------|  
|Среда выполнения отслеживания|Предоставляет инфраструктуру для передачи записей отслеживания.|  
|Участники отслеживания|Потребляет записи отслеживания. [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] поставляется с участником отслеживания, который записывает записи отслеживания в виде событий средства трассировки событий для Windows (ETW).|  
|Профиль отслеживания|Механизм фильтрации, который позволяет участнику отслеживания подписаться на подмножество записей отслеживания, передаваемых из экземпляра рабочего процесса.|  
  
 Следующая таблица содержит подробные сведения о записях отслеживания, создаваемых средой выполнения рабочего процесса.  
  
|Запись отслеживания|Описание|  
|---------------------|-----------------|  
|Записи отслеживания экземпляра рабочего процесса.|Описывает жизненный цикл экземпляра рабочего процесса. Например, запись экземпляра создается при запуске и завершении рабочего процесса.|  
|Записи отслеживания состояний действия.|Подробные сведения о выполнении действия. Эти записи сообщают о состоянии действия рабочего процесса, например о планировании выполнения действия, о завершении действия или о возникновении ошибки.|  
|Запись возобновления закладки.|Создается при возобновлении закладки в экземпляре рабочего процесса.|  
|Пользовательские записи отслеживания.|Автор рабочего процесса может создавать настраиваемые записи отслеживания и выдавать их в рамках пользовательской операции.|  
  
 Участник отслеживания подписывается на часть создаваемых объектов <xref:System.Activities.Tracking.TrackingRecord>, используя профили отслеживания. Профиль отслеживания содержит запросы отслеживания, которые позволяют подписываться на определенный тип записей отслеживания. Профили отслеживания можно указывать в коде или в конфигурации.  
  
### <a name="custom-tracking-participant"></a>Настраиваемый участник отслеживания  
 API участника отслеживания позволяет расширить среду выполнения отслеживания с помощью пользовательского участника отслеживания, который может включать настраиваемую логику для обработки <xref:System.Activities.Tracking.TrackingRecord> объектов, созданных средой рабочего процесса.  
  
 Чтобы создать участника отслеживания, пользователь должен реализовать <xref:System.Activities.Tracking.TrackingParticipant>. В частности, метод <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> должен быть реализован настраиваемым участником. Этот метод вызывается, когда <xref:System.Activities.Tracking.TrackingRecord> создается средой рабочего процесса.  
  
```csharp  
public abstract class TrackingParticipant  
{  
    protected TrackingParticipant();  
  
    public virtual TrackingProfile TrackingProfile { get; set; }  
    public abstract void Track(TrackingRecord record, TimeSpan timeout);  
}  
```  
  
 Полный участник отслеживания реализуется в файле ConsoleTrackingParticipant.cs. Следующий пример кода показывает метод <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> для настраиваемого участника отслеживания.  
  
```csharp  
protected override void Track(TrackingRecord record, TimeSpan timeout)  
{  
    ...             
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;  
    if (workflowInstanceRecord != null)  
    {  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " Workflow InstanceID: {0} Workflow instance state: {1}",  
            record.InstanceId, workflowInstanceRecord.State));  
    }  
  
    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;  
    if (activityStateRecord != null)  
    {  
        IDictionary<String, object> variables = activityStateRecord.Variables;  
        StringBuilder vars = new StringBuilder();  
  
        if (variables.Count > 0)  
        {  
            vars.AppendLine("\n\tVariables:");  
            foreach (KeyValuePair<string, object> variable in variables)  
            {     
                vars.AppendLine(String.Format(  
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));  
            }  
        }  
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,  
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",  
                activityStateRecord.Activity.Name, activityStateRecord.State,  
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));  
    }  
  
    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;  
  
    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))  
    {  
        ...  
    }  
    Console.WriteLine();  
  
}  
```  
  
 Следующий пример кода добавляет консольного участника к средству вызова рабочего процесса.  
  
```csharp  
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()  
{  
    ...  
    // The tracking profile is set here, refer to Program.CS  
...  
}  
  
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());  
invoker.Extensions.Add(customTrackingParticipant);  
```  
  
### <a name="emitting-custom-tracking-records"></a>Выдача пользовательских записей отслеживания  
 В этом образце также демонстрируется возможность создания <xref:System.Activities.Tracking.CustomTrackingRecord> объектов из пользовательских действий рабочего процесса:  
  
-   Объекты <xref:System.Activities.Tracking.CustomTrackingRecord> создаются и заполняются определенными пользователем данными, которые, по замыслу пользователя, будут выдаваться вместе с записью.  
  
-   <xref:System.Activities.Tracking.CustomTrackingRecord> Создается путем вызова метода отслеживания <xref:System.Activities.ActivityContext>.  
  
 В следующем примере продемонстрировано создание <xref:System.Activities.Tracking.CustomTrackingRecord> объектов в рамках пользовательской операции.  
  
```csharp  
// Create the Custom Tracking Record  
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")  
{  
    Data =   
    {  
        {"OrderId", 200},  
        {"OrderDate", "20 Aug 2001"}  
    }  
};  
  
// Emit custom tracking record  
context.Track(customRecord);  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения CustomTrackingSample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
