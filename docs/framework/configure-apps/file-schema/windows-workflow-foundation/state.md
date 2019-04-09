---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108179"
---
# <a name="state"></a>\<Состояние >
Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<состояния >  
\<Состояние >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Строка, указывающая состояние подписки отслеживаемого экземпляра рабочего потока в момент создания записи отслеживания.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<состояния >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.|  
  
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
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
