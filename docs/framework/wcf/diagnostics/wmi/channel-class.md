---
title: "Класс Channel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Класс Channel
Канал  
  
## Синтаксис  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## Методы  
 Класс Channel не определяет никаких методов.  
  
## Свойства  
 Класс Channel имеет следующие свойства.  
  
### LocalAddress  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Локальная конечная точка канала.  
  
### ref  
 Тип данных: Endpoint  
  
 Тип доступа: только для чтения  
  
 Ссылка на конечную точку, к которой подключается канал.  
  
### RemoteAddress  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Удаленный адрес, связанный с каналом.  
  
### SessionId  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Идентификатор текущего сеанса, если он существует.  
  
### Тип  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип канала.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.ChannelBase>