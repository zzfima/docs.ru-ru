---
title: '&lt;faultPropagationQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: cf582fce4e899e62daa4f34f193a0232ec19a135
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149037"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a>&lt;faultPropagationQuery&gt; (WCF)

Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку. Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия. Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.  
  
Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel >  
\<Отслеживание >  
\<профили >  
\<trackingProfile >  
\<рабочий процесс >  
\<faultPropagationQueries >  
\<faultPropagationQuery >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
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
|`faultSourceActivityName`|Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку. По умолчанию используется \*, которое указывает, что записи распространения ошибок возвращаются для всех действий.|  
|`faultHandlerActivityName`|Строка, указывающая имя действия, ставшего источником ошибки.|  
  
### <a name="child-elements"></a>Дочерние элементы

Отсутствует.
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<faultPropagationQueries >](faultpropagationqueries-of-wcf.md)|Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.|
  
## <a name="see-also"></a>См. также  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
