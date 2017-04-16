---
title: "&lt;callbackTimeouts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;callbackTimeouts&gt;
Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.  
  
## Синтаксис  
  
```  
  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`transactionTimeout`|Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.  Значение по умолчанию \- 00:00:00.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>