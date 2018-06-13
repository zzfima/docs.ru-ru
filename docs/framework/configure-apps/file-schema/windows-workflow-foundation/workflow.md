---
title: '&lt;рабочий процесс&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: dc7c693fb2d8b47c0b968eb51cc59327fe43bcc0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758650"
---
# <a name="ltworkflowgt"></a>&lt;рабочий процесс&gt;
Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **ГИПЕРССЫЛКУ "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx» ctivityDefinitionId** свойство.  
  
 Дополнительные сведения об отслеживании рабочих процессов и их конфигурации см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel >  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
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
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|activityDefinitionId|Строка, указывающая идентификатор определения действия отслеживаемого рабочего процесса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<activityScheduledQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием. Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.|  
|[\<activityStateQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса. Например можно хранить список каждый раз завершение действия «Send E-Mail» внутри экземпляра рабочего процесса. Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия. Состояния, доступные для подписки, указаны в ActivtyStates.|  
|[\<bookmarkResumptionQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса. Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.|  
|[\<cancelRequestedQueries>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием. Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.|  
|[\<customTrackingQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода. Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.|  
|[\<faultPropagationQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку. Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия. Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.|  
|[\<workflowInstanceQueries>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<trackingProfile >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|Представляет раздел конфигурации для создания подписки на записи в участнике отслеживания отслеживания рабочего процесса. Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса. Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.|  
  
## <a name="remarks"></a>Примечания  
 Профили отслеживания содержат запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в результате изменения состояния экземпляра рабочего процесса в ходе выполнения. Этот элемент конфигурации определяет отслеживаемый экземпляр рабочего процесса.  
  
 Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе. И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего процесса выполнения.  
  
 Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания. Существует множество типов запросов, которые позволяют подписываться на различные классы записей отслеживания. Полный список запросов см. в разделе список дочерних элементов в этом разделе и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
 В следующем примере показано профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписаться на `Started` и `Completed` события рабочего процесса.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
