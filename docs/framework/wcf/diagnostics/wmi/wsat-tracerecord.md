---
title: "WSAT_TraceRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# WSAT_TraceRecord
WSAT\_TraceRecord  
  
## Синтаксис  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## Методы  
 Класс WSAT\_TraceRecord не определяет никаких методов.  
  
## Свойства  
 Класс WSAT\_TraceRecord имеет следующие свойства.  
  
### ActivityID  
 Тип данных: объект  
Тип доступа: только для чтения  
  
 ИД активности записи трассировки.  
  
### EventID  
 Тип данных: sint32  
Тип доступа: только для чтения  
  
 ИД события записи трассировки.  
  
### TraceRecord  
 Тип данных: string  
Тип доступа: только для чтения  
  
 Запись трассировки  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|