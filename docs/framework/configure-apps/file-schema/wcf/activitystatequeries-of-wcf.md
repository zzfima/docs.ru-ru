---
title: '&lt;activityStateQueries&gt; (WCF)'
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 2dabfdd248006de60b5e84e739f78e03f364dde3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146190"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a>&lt;activityStateQueries&gt; (WCF)

Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса. Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса. Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия. Состояния, доступные для подписки, указаны в ActivtyStates.

Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).

\<system.serviceModel >  
\<Отслеживание >  
\<профили >  
\<trackingProfile >  
\<рабочий процесс >  
\<activityStateQueries >  

## <a name="syntax"></a>Синтаксис  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
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
|[\<activityStateQuery >](activitystatequery-of-wcf.md)|Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.  Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<рабочий процесс >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.|

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
