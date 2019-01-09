---
title: '&lt;customTrackingQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: f75c6bf50d30da5a136137c858a5cd96ce0783ff
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150088"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a>&lt;customTrackingQueries&gt; (WCF)

Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода. Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).
  
\<system.serviceModel >  
\<Отслеживание >  
\<профили >  
\<trackingProfile >  
\<рабочий процесс >  
\<customTrackingQueries >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
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
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<customTrackingQuery >](customtrackingquery-of-wcf.md)|Запрос, который используется для отслеживания событий, определенных в действиях кода.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<рабочий процесс >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
