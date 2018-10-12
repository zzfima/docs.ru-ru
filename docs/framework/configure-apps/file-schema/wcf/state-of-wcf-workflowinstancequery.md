---
title: '&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 427cba7a51bfb908171e476cd703c6a40fd6e144
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123219"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a>&lt;state&gt; (WCF), &lt;workflowInstanceQuery&gt;
Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel >  
\<Отслеживание >  
\<профили >  
\<trackingProfile >  
\<рабочий процесс >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<состояния >  
\<Состояние >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name"/>
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
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
|`name`|Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.|  
  
### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|  
|-------------|-----------------|  
|[\<состояния >](states-of-wcf-workflowinstancequery.md)|Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.|  
  
## <a name="remarks"></a>Примечания  

Возвращаемые записи фильтруются по состояниям в этой коллекции.  
  
В следующей таблице описаны допустимые значения состояния:
  
|Регион|Описание|  
|-----------|-----------------|  
|Прерывание|Экземпляр рабочего процесса прерван.|  
|Завершение|Выполнение экземпляра рабочего процесса завершено.|  
|Deleted|Экземпляр рабочего процесса удален.|  
|Бездействие|Экземпляр рабочего процесса простаивает.|  
|Сохранение|Экземпляр рабочего процесса сохранен.|  
|Возобновление|Экземпляр рабочего процесса возобновлен.|  
|Запуск|Экземпляр рабочего процесса запущен.|  
|UnhandledException|Экземпляр рабочего процесса встретил необработанное исключение.|  
|выгружаемые|Экземпляр рабочего процесса выгружен.|  
|Отменено|Выполнение экземпляра рабочего процесса отменено.|  
|Приостановлено|Выполнение экземпляра рабочего процесса приостановлено.|  
|Завершение|Выполнение экземпляра рабочего процесса завершено.|  
|Возобновлено|Выполнение экземпляра рабочего процесса возобновлено.|  
  
## <a name="example"></a>Пример

При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.  
  
```xml
<workflowInstanceQueries>
  <workflowInstanceQuery>  
    <states>  
      <state name="Started"/>  
    </states>  
  </workflowInstanceQuery>  
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
