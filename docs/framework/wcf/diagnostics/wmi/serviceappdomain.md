---
title: "ServiceAppDomain | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceAppDomain
Сопоставляет службу с доменом приложения.  
  
## Синтаксис  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## Методы  
 Класс ServiceAppDomain не определяет никаких методов.  
  
## Свойства  
 Класс ServiceAppDomain имеет следующие свойства.  
  
### ref  
 Тип данных: Service               
 Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Служба этого домена приложения.  
  
### ref  
 Тип данных: AppDomainInfo               
 Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Содержит свойства домена приложения.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|