---
title: "ActivityTransfer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# ActivityTransfer
Событие перенаправления действия  
  
## Синтаксис  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## Методы  
 Класс ActivityTransfer не определяет никакие методы.  
  
## Свойства  
 Класс ActivityTransfer имеет следующие свойства.  
  
### ActivityID  
  
-   Тип данных: объект                   
     Тип доступа: только для чтения  
  
-   Идентификатор действия  
  
### RelatedActivityID  
  
-   Тип данных: объект                   
     Тип доступа: только для чтения  
  
-   Связанный идентификатор действия  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|