---
title: "&lt;workflow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;workflow&gt;
Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством **activityDefinitionId**.  
  
 Дополнительные сведения об отслеживании рабочих процессов и их конфигурации см. в разделах [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md) и [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Синтаксис  
  
```vb  
  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|activityDefinitionId|Строка, указывающая идентификатор определения действия отслеживаемого рабочего процесса.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<activityScheduledQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.  Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.|  
|[\<activityStateQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.  Например, можно отслеживать завершение действия “Send E\-Mail” внутри экземпляра рабочего процесса.  Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.  Состояния, доступные для подписки, указаны в ActivtyStates.|  
|[\<bookmarkResumptionQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.  Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.|  
|[\<cancelRequestedQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.  Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.|  
|[\<customTrackingQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.  Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.|  
|[\<faultPropagationQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.  Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.  Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.|  
|[\<workflowInstanceQueries\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<trackingProfile\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|Представляет раздел конфигурации для создания подписки на записи отслеживания рабочего процесса в участнике отслеживания.  Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.  Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.|  
  
## Заметки  
 Профили отслеживания содержат запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в результате изменения состояния экземпляра рабочего процесса в ходе выполнения.  Этот элемент конфигурации определяет отслеживаемый экземпляр рабочего процесса.  
  
 Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.  И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего процесса выполнения.  
  
 Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.  Существует множество типов запросов, которые позволяют подписаться на различные классы записей отслеживания.  Полный список запросов см. в списке дочерних элементов в этом разделе, а также в разделе [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
 В следующем примере показан профиль отслеживания в файле конфигурации, с помощью которого участник отслеживания может подписаться на события рабочего процесса `Started`и `Completed`.  
  
```  
  
<system.serviceModel>  
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
</system.serviceModel>  
  
```  
  
## См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>   
 <xref:System.Activities.Tracking.TrackingProfile>   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)