---
title: "MustUnderstandBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# MustUnderstandBehavior
MustUnderstandBehavior  
  
## Синтаксис  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## Методы  
 Класс MustUnderstandBehavior не определяет никаких методов.  
  
## Свойства  
 Класс MustUnderstandBehavior содержит следующие свойства:  
  
### ValidateMustUnderstand  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Если логическое значение равно `true`, все заголовки SOAP с атрибутом `MustUnderstand` не обрабатываются, потому что поведение создало исключение.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>