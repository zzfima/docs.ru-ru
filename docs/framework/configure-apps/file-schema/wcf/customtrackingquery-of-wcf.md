---
title: <customTrackingQuery>WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919363"
---
# <a name="customtrackingquery-of-wcf"></a>\<Кустомтраккингкуери > WCF

Представляет запрос, который используется для трассировки событий, определенных в действиях кода. Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.

Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .  
  
\<> System. serviceModel  
\<Отслеживание >  
\<Профили >  
\<trackingProfile >  
\<> рабочего процесса  
\<Кустомтраккингкуериес >  
\<Кустомтраккингкуери >  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`activityName`|Строка, задающая имя действия, сформировавшего запись отслеживания.|  
|`name`|Строка, задающая имя выдаваемой пользовательской записи отслеживания.|  
  
### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|  
|-------------|-----------------|  
|[\<Кустомтраккингкуериес >](customtrackingqueries-of-wcf.md)|Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.|
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md)
