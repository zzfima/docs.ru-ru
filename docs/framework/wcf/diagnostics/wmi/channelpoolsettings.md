---
title: "ChannelPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ChannelPoolSettings
ChannelPoolSettings  
  
## Синтаксис  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## Методы  
 Класс ChannelPoolSettings не определяет никаких методов.  
  
## Свойства  
 Класс ChannelPoolSettings имеет следующие свойства.  
  
### IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### LeaseTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время ожидания завершения операции аренды.  
  
### MaxOutboundChannelsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих каналов для каждой конечной точки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>