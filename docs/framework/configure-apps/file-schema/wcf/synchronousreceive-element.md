---
title: "Элемент &lt;synchronousReceive&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Элемент &lt;synchronousReceive&gt;
Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.  Он не имеет атрибутов или дочерних элементов.  
  
## Синтаксис  
  
```  
  
<synchronousReceive />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## Заметки  
 Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] создает новый поток переноса сообщений для каждого принятого канала.  При наличии множества каналов существует вероятность недостатка потоков.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>   
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>