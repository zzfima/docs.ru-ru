---
title: "AppDomainInfo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# AppDomainInfo
Сведения о домене приложения  
  
## Синтаксис  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## Методы  
 Класс AppDomainInfo не определяет никакие методы.  
  
## Свойства  
 Класс AppDomainInfo имеет следующие свойства.  
  
### AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения.  
  
### IsDefault  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, является ли домен приложения доменом приложения, используемым по умолчанию.  
  
### LogMalformedMessages  
 Тип данных: boolean  
  
 Тип доступа: чтение\/запись  
  
 Значение, указывающее, заносятся ли в журнал неправильные сообщения.  
  
### LogMessagesAtServiceLevel  
 Тип данных: boolean  
  
 Тип доступа: чтение\/запись  
  
 Значение, указывающее, трассируются ли сообщения на уровне службы \(перед шифрованием и преобразованиями, связанными с транспортом\).  
  
### LogMessagesAtTransportLevel  
 Тип данных: boolean  
  
 Тип доступа: чтение\/запись  
  
 Значение, указывающее, трассируются ли сообщения на уровне транспорта.  
  
### MessageLoggingTraceListeners  
 Тип данных: массив TraceListener  
  
 Тип доступа: только для чтения  
  
 Коллекция прослушивателей трассировки, которые ожидают передачи данных источнику трассировки System.Wmi.MessageLogging.  
  
### Name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя домена приложения.  
  
### PerformanceCounters  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Область активных счетчиков производительности в домене приложения.  
  
### ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор процесса.  
  
### ServiceConfigPath  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Путь к конфигурации службы.  
  
### TraceLevel  
 Тип данных: string  
  
 Тип доступа: чтение\/запись  
  
 Уровень трассировки источника трассировки System.Wmi.  
  
### ServiceModelTraceListeners  
 Тип данных: массив TraceListener  
  
 Тип доступа: только для чтения  
  
 Коллекция прослушивателей, ожидающих передачи данных от источника трассировки System.ServiceModel.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|