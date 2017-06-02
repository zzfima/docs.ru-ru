---
title: "MsmqBindingElementBase | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# MsmqBindingElementBase
MsmqBindingElementBase  
  
## Синтаксис  
  
```  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## Методы  
 Класс MsmqBindingElementBase не определяет никаких методов.  
  
## Свойства  
 Класс MsmqBindingElementBase имеет следующие свойства.  
  
### CustomDeadLetterQueue  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса \(URI\), содержащий местоположение очереди недоставленных сообщений для каждого приложения; в эту очередь помещаются просроченные сообщения или сообщения, которые не удалось передать или доставить.  
  
### DeadLetterQueue  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение перечисления, указывающее тип используемой очереди недоставленных сообщений.  
  
### Durable  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, являются ли сообщения, обрабатываемые этой привязкой, устойчивыми или неустойчивыми.  
  
### ExactlyOnce  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, доставляются ли сообщения, обрабатываемые этой привязкой, только один раз.  
  
### MaxRetryCycles  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество циклов повторных попыток доставить сообщение принимающему приложению.  
  
### ReceiveErrorHandling  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры обработки подозрительных сообщений.  
  
### ReceiveRetryCount  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество немедленных повторных попыток считывания сообщения из очереди приложения.  
  
### RetryCycleDelay  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее временную задержку между циклами повторных попыток доставить сообщение, которое не удалось доставить немедленно.  
  
### TimeToLive  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Промежуток времени, соответствующий максимальному сроку нахождения в очереди сообщений, обрабатываемых этой привязкой.  
  
### UseMsmqTracing  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, следует ли трассировать сообщения, обрабатываемые этой привязкой.  
  
### UseSourceJournal  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, должны ли сохраняться в очереди журнала источника копии сообщений, обрабатываемых этой привязкой.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.NetMsmqBinding>   
 <xref:System.ServiceModel.MsmqBindingBase>