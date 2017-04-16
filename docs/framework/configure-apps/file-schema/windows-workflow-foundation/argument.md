---
title: "&lt;argument&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;argument&gt;
Элемент конфигурации, который представляет аргумент, связанный с запросом состояния действия.  
  
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
|имя|Строка, задающая имя аргумента.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|Коллекция аргументов, связанных с этим запросом действия.|  
  
## Заметки  
 Уникальной функцией ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.  Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.  С помощью элементов [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) можно извлекать любые переменные или аргументы из любого действия в рабочем процессе. В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.  Переменные и аргументы можно извлекать только при помощи ActivityStateRecord, поэтому подписка на них выполняется в рамках профиля отслеживания с помощью запроса [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
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
 [System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)