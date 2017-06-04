---
title: "ServiceToEndpointAssociation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceToEndpointAssociation
Сопоставляет службу конечной точке.  
  
## Синтаксис  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## Методы  
 Класс ServiceToEndpointAssociation не определяет никаких методов.  
  
## Свойства  
 Класс ServiceToEndpointAssociation имеет следующие свойства.  
  
### ref  
 Тип данных: Service  
  
 Тип доступа: только для чтения  
Квалификаторы: ключ  
  
 Служба, связанная с конечной точкой.  
  
### ref  
 Тип данных: Endpoint  
  
 Тип доступа: только для чтения  
Квалификаторы: ключ  
  
 Конечная точка, связанная со службой.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|