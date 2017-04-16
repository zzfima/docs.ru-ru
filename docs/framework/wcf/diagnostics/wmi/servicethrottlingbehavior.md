---
title: "ServiceThrottlingBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## Синтаксис  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## Методы  
 Класс ServiceThrottlingBehavior не определяет никаких методов.  
  
## Свойства  
 Класс ServiceThrottlingBehavior имеет следующие свойства.  
  
### MaxConcurrentCalls  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество сообщений, которые могут одновременно обрабатываться во всех объектах диспетчера в узле ServiceHost.  
  
### MaxConcurrentInstances  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число объектов службы, которые могут выполняться одновременно.  
  
### MaxConcurrentSessions  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число сеансов, одновременно принимаемых узлом.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>