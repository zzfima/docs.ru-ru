---
title: "BinaryMessageEncodingBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# BinaryMessageEncodingBindingElement
BinaryMessageEncodingBindingElement  
  
## Синтаксис  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## Методы  
 Класс BinaryMessageEncodingBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс BinaryMessageEncodingBindingElement имеет следующие свойства.  
  
## MaxReadPoolSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  
  
## MaxSessionSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее максимальный размер буфера, используемого для кодирования \(в байтах\).  
  
## MaxWritePoolSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  
  
## ReaderQuotas  
 Тип данных: XmlDictionaryReaderQuotas  
  
 Тип доступа: только для чтения  
  
 Квоты средств чтения.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>