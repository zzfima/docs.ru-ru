---
title: "ServiceMetadataBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## Синтаксис  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## Методы  
 Класс ServiceMetadataBehavior не определяет никаких методов.  
  
## Свойства  
 Класс ServiceMetadataBehavior имеет следующие свойства.  
  
### ExternalMetadataLocation  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение, в которое служба перенаправляет запросы метаданных.  
  
### HttpGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### HttpGetUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение, в котором публикуется код WSDL службы для извлечения по протоколу HTTP.  
  
### HttpsGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой код WSDL через HTTPS по адресу, определяемому атрибутом `HttpsGetUrl`.  
  
### HttpsGetUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение, в котором публикуется код WSDL службы для извлечения по протоколу HTTPS.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>