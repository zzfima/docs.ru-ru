---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073126"
---
# <a name="states"></a>\<состояния >
Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<состояния >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
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
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Состояние >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<workflowInstanceQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемые записи фильтруются по состояниям в этой коллекции.  
  
 Допустимые значения состояния описаны в следующей таблице.  
  
|Регион|Описание|  
|-----------|-----------------|  
|Прерывание|Экземпляр рабочего процесса прерван.|  
|Завершено|Выполнение экземпляра рабочего процесса завершено.|  
|Deleted|Экземпляр рабочего процесса удален.|  
|Бездействие|Экземпляр рабочего процесса простаивает.|  
|Сохранение|Экземпляр рабочего процесса сохранен.|  
|Возобновление|Экземпляр рабочего процесса возобновлен.|  
|Запуск|Экземпляр рабочего процесса запущен.|  
|UnhandledException|Экземпляр рабочего процесса встретил необработанное исключение.|  
|Выгружен|Экземпляр рабочего процесса выгружен.|  
|Отменено|Выполнение экземпляра рабочего процесса отменено.|  
|Приостановлена|Выполнение экземпляра рабочего процесса приостановлено.|  
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
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
