---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 1a6899eaa04ad16192e07f4bc2ad1abe6e4aedd5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257373"
---
# <a name="faultpropagationquery"></a>\<faultPropagationQuery>
Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку. Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия. Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel>  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<faultPropagationQueries>  
\<faultPropagationQuery>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|activityName|Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку. Значение по умолчанию - «*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.|  
|faultHandlerActivityName|Строка, указывающая имя действия, ставшего источником ошибки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<faultPropagationQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
