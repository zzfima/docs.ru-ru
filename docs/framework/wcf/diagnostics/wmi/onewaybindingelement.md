---
title: "OneWayBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OneWayBindingElement
OneWayBindingElement  
  
## Синтаксис  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## Методы  
 Класс OneWayBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс OneWayBindingElement имеет следующие свойства.  
  
### ChannelPoolSettings  
 Тип данных: ChannelPoolSettings  
  
 Тип доступа: только для чтения  
  
 Параметры пула каналов.  
  
### MaxAcceptedChannels  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число принимаемых каналов.  
  
### PacketRoutable  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, возможна ли маршрутизация пакета.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>