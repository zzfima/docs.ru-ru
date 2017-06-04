---
title: "TcpConnectionPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# TcpConnectionPoolSettings
TcpConnectionPoolSettings  
  
## Синтаксис  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## Методы  
 Класс TcpConnectionPoolSettings не определяет никаких методов.  
  
## Свойства  
 Класс TcpConnectionPoolSettings имеет следующие свойства.  
  
### GroupName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### LeaseTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время ожидания завершения выполнения операции аренды.  
  
### MaxOutboundConnectionsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих подключений для каждой конечной точки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>