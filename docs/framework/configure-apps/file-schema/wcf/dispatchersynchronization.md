---
title: "&lt;dispatcherSynchronization&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;dispatcherSynchronization&gt;
Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.  
  
## Синтаксис  
  
```  
  
<dispatcherSynchronizationBehavior   
   asynchronousSendEnabled=”Boolean”  
   maxPendingReceives="Integer" />  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|asynchronousSendEnabled|Логическое значение, указывающее, включено ли поведение, которое позволяет отправлять ответы в асинхронном режиме.|  
|`maxPendingReceives`|Целочисленное значение, которое указывает число возможных получений по одному каналу.<br /><br /> Это значение должно настраиваться только после правильной настройки поведения регулирования службы.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.DispatcherSynchronizationBehaviorElement>   
 <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>