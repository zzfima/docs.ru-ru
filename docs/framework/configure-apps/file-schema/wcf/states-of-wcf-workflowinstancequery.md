---
title: '&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef3d8d05dad684b07ee527dbd34ae6269ae57657
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a>&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;
Представляет коллекцию состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
 \<system.serviceModel >  
\<Отслеживание >  
\<trackingProfile >  
\<рабочий процесс >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<состояния >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<состояния >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Подписанное состояние от экземпляра рабочего процесса, который отслеживается в момент создания записи отслеживания.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<workflowInstanceQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемые записи фильтруются по состояниям в этой коллекции.  
  
 Допустимые значения состояния описаны в следующей таблице.  
  
|Состояние|Описание|  
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
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
