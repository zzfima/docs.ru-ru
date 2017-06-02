---
title: "&lt;cancelRequestedQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;cancelRequestedQuery&gt;
Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.  Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.  
  
 Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Синтаксис  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|activityName|Строка, задающая имя действия, которое запрашивает отмену.|  
|childActivityName|Строка, указывающая имя дочернего действия, для которого была запрошена отмена.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<faultPropagationQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.  Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.|  
  
## См. также  
 [System.ServiceModel.Activities.Tracking.Configuration.CancelRequestQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.CancelRequestQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.CancelRequestedQuery](assetId:///System.Activities.Tracking.CancelRequestedQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Профили отслеживания](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)