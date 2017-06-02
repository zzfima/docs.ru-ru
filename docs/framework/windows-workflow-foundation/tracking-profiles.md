---
title: "Профили отслеживания | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Профили отслеживания
Профили отслеживания содержат запросы отслеживания, позволяющие участнику подписываться на события рабочего потока, создаваемые в момент изменения состояния экземпляра рабочего процесса во время выполнения.  
  
## Профили отслеживания  
 Профили отслеживания используются для определения того, какие данные отслеживания создаются для экземпляра рабочего процесса.Если этот профиль не указан, создаются все события отслеживания.Если профиль указан, будут создаваться события, определенные в профиле отслеживания.Исходя из потребностей можно написать профиль с обычной гранулярностью, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для воспроизведения всего процесса выполнения в дальнейшем.  
  
 Профили отслеживания ведут себя как XML\-элементы в файле стандартной конфигурации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] или как заданный блок кода.В следующем примере показан профиль отслеживания [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] в файле конфигурации, который позволяет участнику отслеживания подписаться на события рабочих процессов `Started` и `Completed`.  
  
```  
<system.serviceModel>  
    ...  
    <tracking>    
      <trackingProfile name="Sample Tracking Profile">  
        <workflow activityDefinitionId="*">  
          <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                <state name="Started"/>  
                <state name="Completed"/>  
              </states>  
            </workflowInstanceQuery>  
          </workflowInstanceQueries>  
        </workflow>  
      </trackingProfile>          
    </profiles>  
  </tracking>  
    ...  
</system.serviceModel>  
  
```  
  
 В следующем примере показан соответствующий профиль отслеживания, созданный с помощью кода.  
  
```csharp  
TrackingProfile profile = new TrackingProfile()  
{  
    Name = "CustomTrackingProfile",  
    Queries =   
    {  
        new WorkflowInstanceQuery()  
        {  
            // Limit workflow instance tracking records for started and  
            // completed workflow states.  
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },  
        }  
    }  
};  
  
```  
  
 Записи отслеживания фильтруются посредством режима видимости в рамках профиля отслеживания при помощи атрибута <xref:System.Activities.Tracking.ImplementationVisibility>.Композитное действие является действием верхнего уровня, которое содержит другие действия, образующие его реализацию.Режим видимости задает записи отслеживания, созданные из композитных действий в действии рабочего процесса, с целью указания, отслеживаются ли действия, образующие реализацию.Режим видимости применяется на уровне профиля отслеживания.Фильтрацией записей отслеживания для отдельно взятых действий в рабочем процессе управляют при помощи запросов в профиле отслеживания.Дополнительные сведения см. в разделе **Типы запросов профиля отслеживания** в этом документе.  
  
 Два режима видимости, задаваемые атрибутом `implementationVisibility` в профиле отслеживания, — `RootScope` и `All`.Использование режима `RootScope` удаляет записи отслеживания для действий, образующих реализацию действия в том случае, когда композитное действие не является корневым действием в рабочем процессе.Это предполагает, что, когда действие, реализуемое при помощи других действий, добавляется в рабочий процесс и параметр `implementationVisibility` имеет значение RootScope, будут отслеживаться только события верхнего уровня внутри этого композитного действия.Если действие является корневым для рабочего процесса, реализация действия — это сам рабочий процесс, а записи отслеживания создаются для действий, образующих реализацию.Использование режима «Все» позволяет создавать записи отслеживания для корневого действия и всех его композитных действий.  
  
 Например, предположим, что *MyActivity* является композитным действием, реализация которого содержит два действия — *Activity1* и *Activity2*.При добавлении этого действия в рабочий процесс и включении отслеживания \(профиль отслеживания `implementationVisibility` получает значение `RootScope`\) записи отслеживания создаются только для *MyActivity*.Однако записи не создаются для действий *Activity1* и *Activity2*.  
  
 Теперь, если атрибут `implementationVisisbility` для профиля отслеживания получит значение `All`, записи отслеживания будут создаваться не только для *MyActivity*, но также для действий *Activity1* и *Activity2*.  
  
 Флажок `implementationVisibility` применяется для следующих типов записей отслеживания:  
  
-   ActivityStateRecord  
  
-   FaultPropagationRecord  
  
-   CancelRequestedRecord  
  
-   ActivityScheduledRecord  
  
> [!NOTE]
>  Запись CustomTrackingRecords, создаваемая из реализации действия, не фильтруется параметром implementationVisibility.  
  
 Функция `implementationVisibility` задается в профиле отслеживания в коде как <xref:System.Activities.Tracking.ImplementationVisibility> следующим образом:  
  
```  
TrackingProfile sampleTrackingProfile = new TrackingProfile()  
{  
    Name = "Sample Tracking Profile",  
    ImplementationVisibility = ImplementationVisibility.RootScope  
};  
  
```  
  
 Функция `implementationVisibility` задается в профиле отслеживания в файле конфигурации как <xref:System.Activities.Tracking.ImplementationVisibility> следующим образом:  
  
```  
<tracking>  
      <profiles>  
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">  
          <workflow activityDefinitionId="*">  
...  
         </workflow>  
        </trackingProfile>  
      </profiles>  
</tracking>  
  
```  
  
 Параметр `ImplementationVisibility` в профиле отслеживания является необязательным.По умолчанию он имеет значение `RootScope`.Значения для этого атрибута также учитывают регистр.  
  
### Отслеживание типов запросов профиля  
 Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.Существует множество типов запросов, которые позволяют подписаться на различные классы объектов <xref:System.Activities.Tracking.TrackingRecord>.Профили отслеживания могут быть заданы в конфигурации или посредством кода.Ниже приводятся наиболее распространенные типы запросов.  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceQuery> — используйте этот запрос для отслеживания изменений жизненного цикла экземпляра рабочего процесса, таких как ранее представленные события `Started` и `Completed`.Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
     Состояния, на которые можно подписаться, задаются классом <xref:System.Activities.Tracking.WorkflowInstanceStates>.  
  
     Конфигурация или код, используемые для подписки на записи отслеживания на уровне экземпляра рабочего процесса для состояния экземпляра `Started` при помощи запроса <xref:System.Activities.Tracking.WorkflowInstanceQuery>, показаны в следующем примере.  
  
    ```  
    <workflowInstanceQueries>  
        <workflowInstanceQuery>  
          <states>  
            <state name="Started"/>  
          </states>  
        </workflowInstanceQuery>  
    </workflowInstanceQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new WorkflowInstanceQuery()  
            {  
                States = { WorkflowInstanceStates.Started}                                                                     
            }  
        }  
    };  
  
    ```  
  
-   <xref:System.Activities.Tracking.ActivityStateQuery> — используйте этот запрос для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.Например, можно отслеживать завершение действия «Send E\-Mail» внутри экземпляра рабочего процесса.Этот запрос необходим, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.ActivityStateRecord>.Состояния, доступные для подписки, указаны в <xref:System.Activities.Tracking.ActivityStates>.  
  
     Конфигурация и код, используемые для подписки на записи отслеживания состояний действий при помощи запроса <xref:System.Activities.Tracking.ActivityStateQuery> для действия `SendEmailActivity`, показаны в следующем примере.  
  
    ```  
    <activityStateQueries>  
      <activityStateQuery activityName="SendEmailActivity">  
        <states>  
          <state name="Closed"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new ActivityStateQuery()  
            {                              
                ActivityName = "SendEmailActivity",  
                States = { ActivityStates.Closed }  
            }  
        }  
    };  
  
    ```  
  
    > [!NOTE]
    >  Если несколько элементов activityStateQuery имеют одинаковые имена, то только состояния в последнем элементе используются в профиле отслеживания.  
  
-   <xref:System.Activities.Tracking.ActivityScheduledQuery> — этот запрос позволяет отслеживать действие, запланированное к исполнению родительским действием.Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
     Конфигурация и код, используемые для подписки на записи, связанные с дочерним действием `SendEmailActivity`, планируемым при помощи запроса <xref:System.Activities.Tracking.ActivityScheduledQuery>, показаны в следующем примере.  
  
    ```  
    <activityScheduledQueries>  
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
     </activityScheduledQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new ActivityScheduledQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
  
    ```  
  
-   <xref:System.Activities.Tracking.FaultPropagationQuery> — используйте такой запрос для отслеживания обработки ошибок, возникающих во время действия.Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
     Конфигурация и код, используемые для подписки на записи, связанные с распространением ошибок при помощи запроса <xref:System.Activities.Tracking.FaultPropagationQuery>, показаны в следующем примере.  
  
    ```  
    <faultPropagationQueries>  
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />  
    </faultPropagationQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new FaultPropagationQuery()  
            {  
                FaultSourceActivityName = "SendEmailActivity",  
                FaultHandlerActivityName = "NotificationsFaultHandler"  
            }  
        }  
    };  
  
    ```  
  
-   <xref:System.Activities.Tracking.CancelRequestedQuery> — используйте этот запрос для отслеживания запросов по отмене дочернего действия родительским действием.Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
     Конфигурация и код, используемые для подписки на записи, связанные с отменой действий при помощи запроса <xref:System.Activities.Tracking.CancelRequestedQuery>, показаны в следующем примере.  
  
    ```  
    <cancelRequestedQueries>  
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
    </cancelRequestedQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CancelRequestedQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
  
    ```  
  
-   <xref:System.Activities.Tracking.CustomTrackingQuery> — используйте этот запрос для отслеживания событий, определенных в действиях кода.Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
     Конфигурация и код, используемые для подписки на записи, связанные с пользовательскими записями отслеживания при помощи запроса <xref:System.Activities.Tracking.CustomTrackingQuery>, показаны в следующем примере.  
  
    ```  
    <customTrackingQueries>  
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />  
    </customTrackingQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CustomTrackingQuery()   
            {  
                Name = "EmailAddress",  
                ActivityName = "SendEmailActivity"  
            }  
        }  
    };  
  
    ```  
  
-   <xref:System.Activities.Tracking.BookmarkResumptionQuery> — используйте этот запрос для отслеживания возобновления закладки в экземпляре рабочего процесса.Этот запрос необходим, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
     Конфигурация и код, используемые для подписки на записи, связанные с возобновлением закладок при помощи запроса <xref:System.Activities.Tracking.BookmarkResumptionQuery>, показаны в следующем примере.  
  
    ```  
    <bookmarkResumptionQueries>  
      <bookmarkResumptionQuery name="SentEmailBookmark" />  
    </bookmarkResumptionQueries>  
  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new BookmarkResumptionQuery()  
            {  
                Name = "sentEmailBookmark"  
            }  
        }  
    };  
  
    ```  
  
### Заметки  
 Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.Например, можно добавить тег “Mail Server” \=\= “Mail Server1” к нескольким записям отслеживания из нескольких рабочих процессов.Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.  
  
 Для этого к запросу отслеживания добавляется заметка, как показано в следующем примере.  
  
```  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
  
```  
  
### Создание профиля отслеживания  
 Элементы запроса отслеживания используются для создания профиля отслеживания при помощи XML\-файла конфигурации либо кода [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].Ниже приводится пример профиля отслеживания, созданного при помощи файла конфигурации.  
  
```  
<system.serviceModel>  
  <tracking>  
    <profiles>  
      <trackingProfile name="Sample Tracking Profile ">  
        <workflow activityDefinitionId="*">  
          <!--Specify the tracking profile query elements to subscribe for tracking records-->  
        </workflow>  
      </trackingProfile>  
    </profiles>  
  </tracking>  
</system.serviceModel>  
  
```  
  
> [!WARNING]
>  Для WF с использованием узла служб рабочих процессов профиль отслеживания обычно создается при помощи файла конфигурации.Также можно создать профиль отслеживания при помощи кода, используя профиль отслеживания и API\-интерфейс запросов отслеживания.  
  
 Профиль, настроенный как XML\-файл конфигурации, применяется к участнику отслеживания при помощи поведения.Поведение добавляется к узлу служб рабочих процессов в соответствии с описанием в разделе [Настройка отслеживания рабочего процесса](../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md).  
  
 Детализация записей отслеживания, создаваемых узлом, определяется параметрами конфигурации в профиле отслеживания.Участник отслеживания подписывается на записи отслеживания путем добавления запросов в профиль отслеживания.Для подписки на все записи отслеживания профилю отслеживания нужно указать все запросы отслеживания, используя «\*» в полях имен для каждого запроса.  
  
 Ниже приводятся некоторые распространенные примеры профилей отслеживания.  
  
-   Профиль отслеживания для получения записей экземпляра рабочего процесса и ошибок.  
  
```  
<trackingProfile name="Instance and Fault Records">  
  <workflow activityDefinitionId="*">  
    <workflowInstanceQueries>  
      <workflowInstanceQuery>  
        <states>  
          <state name="*" />  
        </states>  
      </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    <activityStateQueries>  
      <activityStateQuery activityName="*">  
        <states>  
          <state name="Faulted"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  </workflow>  
</trackingProfile>  
  
```  
  
1.  Профиль отслеживания для получения всех пользовательских записей отслеживания.  
  
```  
<trackingProfile name="Instance_And_Custom_Records">  
  <workflow activityDefinitionId="*">  
    <customTrackingQueries>  
      <customTrackingQuery name="*" activityName="*" />  
    </customTrackingQueries>  
  </workflow>  
</trackingProfile>  
  
```  
  
## См. также  
 [Отслеживание SQL](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)   
 [Наблюдение за Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Наблюдение за приложениями с помощью App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)