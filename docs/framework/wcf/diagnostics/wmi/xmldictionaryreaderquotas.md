---
title: "XmlDictionaryReaderQuotas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## Синтаксис  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## Методы  
 Класс XmlDictionaryReaderQuotas не определяет никаких методов.  
  
## Свойства  
 Класс XmlDictionaryReaderQuotas имеет следующие свойства:  
  
### MaxArrayLength  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально допустимая длина массива.  
  
### MaxBytesPerRead  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное допустимое число байтов, возвращаемых для каждой операции чтения.  
  
### MaxDepth  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальная глубина вложенного узла для каждого чтения.  
  
### MaxNameTableCharCount  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное допустимое число символов в имени таблицы.  
  
### MaxStringContentLength  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное допустимое число символов в содержимом элемента XML.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.Xml.XmlDictionaryReaderQuotas>   
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>