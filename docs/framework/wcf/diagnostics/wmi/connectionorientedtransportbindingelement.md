---
title: "ConnectionOrientedTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## Синтаксис  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## Методы  
 Класс ConnectionOrientedTransportBindingElement не определяет никакие методы.  
  
## Свойства  
 Класс ConnectionOrientedTransportBindingElement имеет следующие свойства.  
  
### ChannelInitializationTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Задает интервал времени, который выделяется для инициализации канала до возникновения тайм\-аута.  
  
### ConnectionBufferSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Размер буфера, используемого для передачи по сети фрагмента сериализованного сообщения от клиента серверу.  
  
### HostNameComparisonMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса \(URI\).  
  
### MaxBufferSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально используемый размер буфера.  
  
### MaxOutputDelay  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.  
  
### MaxPendingAccepts  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число ожидающих асинхронных потоков приема, доступных для обработки входящих подключений к службе.  
  
### MaxPendingConnections  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих подключений.  
  
### TransferMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, следует ли буферизировать сообщения, или передавать их потоком с использованием транспорта, ориентированного на подключения.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>