---
title: "ServiceDebugBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceDebugBehavior
ServiceDebugBehavior  
  
## Синтаксис  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## Методы  
 Класс ServiceDebugBehavior не определяет никаких методов.  
  
## Свойства  
 Класс ServiceDebugBehavior имеет следующие свойства.  
  
### HttpHelpPageEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### HttpHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.  
  
### HttpsHelpPageEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.  
  
### HttpsHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.  
  
### IncludeExceptionDetailInFaults  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>