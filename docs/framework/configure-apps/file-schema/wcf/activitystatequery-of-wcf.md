---
title: "&lt;activityStateQuery&gt; (WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;activityStateQuery&gt; (WCF)
Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.  Например, можно отслеживать завершение действия “Send E\-Mail” внутри экземпляра рабочего процесса.  Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.  Состояния, доступные для подписки, указаны в ActivtyStates.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Синтаксис  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <activityStateQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|activityName|Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|Коллекция аргументов, связанных с этим запросом действия.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Коллекция переменных, связанных с этим запросом действия.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<faultPropagationQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.  Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.|  
  
## Заметки  
 Уникальной функцией ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.  Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.  С помощью элементов [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)`Closed` можно извлекать любые переменные или аргументы из любого действия в рабочем процессе. В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия .  Переменные и аргументы можно извлекать только при помощи ActivityStateRecord, поэтому подписка на них выполняется в рамках профиля отслеживания с помощью запроса [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
```  
  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
  
```  
  
## См. также  
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)