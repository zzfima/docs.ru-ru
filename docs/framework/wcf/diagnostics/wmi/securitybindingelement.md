---
title: "SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# SecurityBindingElement
SecurityBindingElement  
  
## Синтаксис  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## Методы  
 Класс SecurityBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс SecurityBindingElement имеет следующие свойства.  
  
### DefaultAlgorithmSuite  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает алгоритмы, используемые в сочетании с привязкой.  
  
### IncludeTimestamp  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, будет ли в каждое сообщение вноситься отметка времени.  
  
### KeyEntropyMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Источник энтропии, используемый для создания ключей.  
  
### LocalServiceSecuritySettings  
 Тип данных: LocalServiceSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Свойства безопасности для локальной службы, соответствующие данной привязке.  
  
### MessageSecurityVersion  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Версия, используемая для безопасности сообщения.  
  
### SecurityHeaderLayout  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Порядок элементов в заголовке безопасности для данной привязки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>