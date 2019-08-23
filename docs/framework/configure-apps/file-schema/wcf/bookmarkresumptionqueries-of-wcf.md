---
title: <bookmarkResumptionQueries>WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919741"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a>\<Букмаркресумптионкуериес > WCF
  
Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса. Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.  
  
Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).
  
\<> System. serviceModel  
\<Отслеживание >  
\<Профили >  
\<trackingProfile >  
\<> рабочего процесса  
\<Букмаркресумптионкуериес >  
\<Букмаркресумптионкуери >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты  
  
В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Букмаркресумптионкуери >](bookmarkresumptionquery-of-wcf.md)|Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса. Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> рабочего процесса](../windows-workflow-foundation/workflow.md)|Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md)
