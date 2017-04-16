---
title: "CustomBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# CustomBindingElement
CustomBindingElement  
  
## Синтаксис  
  
```  
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## Методы  
 Класс CustomBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс CustomBindingElement имеет следующее свойство:  
  
### Имя  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Строка, содержащая имя конфигурации привязки.  Это значение является определяемой пользователем строкой, которая используется как строка идентификации для пользовательской привязки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.CustomBinding>