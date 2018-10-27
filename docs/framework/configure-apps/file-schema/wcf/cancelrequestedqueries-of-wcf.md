---
title: '&lt;cancelRequestedQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 40fbcafd641e93be6ba21635f4f6e6428be62c12
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193790"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a>&lt;cancelRequestedQueries&gt; (WCF)
Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием. Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.  
  
Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel >  
\<Отслеживание >  
\<профили > \<trackingProfile >  
\<рабочий процесс >  
\<cancelRequestedQueries >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты  

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты

Отсутствует.
  
### <a name="child-elements"></a>Дочерние элементы
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<рабочий процесс >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
