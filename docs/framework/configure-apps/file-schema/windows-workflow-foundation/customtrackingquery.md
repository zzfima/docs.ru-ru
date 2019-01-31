---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 4e525bc4c77649a6c6d70ddb2408b6ecce4a0f09
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263773"
---
# <a name="customtrackingquery"></a>\<customTrackingQuery>
Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода. Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<customTrackingQueries >  
\<customTrackingQuery>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|activityName|Строка, задающая имя действия, сформировавшего запись отслеживания.|  
|имя|Строка, задающая имя выдаваемой пользовательской записи отслеживания.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<customTrackingQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|Запрос, который используется для отслеживания событий, определенных в действиях кода.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
