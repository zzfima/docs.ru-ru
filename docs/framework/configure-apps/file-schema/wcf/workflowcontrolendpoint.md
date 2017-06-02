---
title: "&lt;workflowControlEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;workflowControlEndpoint&gt;
Этот элемент конфигурации определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса \(создание, выполнение, приостановка, завершение и т. д.\).  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <workflowControlEndpoint>   
          <standardEndpoint  
                  name="String" />   
       </workflowControlEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Строка, указывающая имя конфигурации стандартной конечной точки.  Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Коллекция стандартных конечных точек, одно или несколько свойств которых \(адрес, привязка, контракт\) являются фиксированными.|  
  
## См. также  
 <xref:System.ServiceModel.Activites.WorkflowControlEndpoint>