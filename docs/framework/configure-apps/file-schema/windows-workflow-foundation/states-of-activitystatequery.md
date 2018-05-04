---
title: '&lt;states&gt; &lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: d26687e9d0f2bee672f6b0c6c38b87fadf6e7888
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a>&lt;states&gt; &lt;activityStateQuery&gt;
Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel >  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<activityStateQueries >  
\<activityStateQuery >  
\<состояния >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Состояние >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|Элемент конфигурации, содержащий состояния подписанного действия, для которого необходимо создать запись отслеживания.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием. Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.|  
  
## <a name="remarks"></a>Примечания  
 Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса. Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения. Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания. Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
