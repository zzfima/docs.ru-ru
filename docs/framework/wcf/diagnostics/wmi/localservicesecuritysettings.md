---
title: "LocalServiceSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## Синтаксис  
  
```  
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## Методы  
 Класс LocalServiceSecuritySettings не определяет никаких методов.  
  
## Свойства  
 Класс LocalServiceSecuritySettings имеет следующие свойства.  
  
### DetectReplays  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, которое указывает, обнаруживаются и обрабатываются ли атаки повторной передачи пакетов против заданного канала автоматически.  
  
### InactivityTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих безопасных сеансов, поддерживаемое службой.  
  
### IssuedCookieLifetime  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает время существования для всех новых файлов безопасности cookie.  
  
### MaxCachedCookies  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество файлов cookie, которые могут быть кэшированы.  
  
### MaxClockSkew  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, указывающее максимальный разброс времени между системными часами взаимодействующих сторон.  
  
### MaxPendingSessions  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих подключений к службе.  
  
### MaxStatefulNegotiations  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Количество одновременно выполняемых согласований режима безопасности.  
  
### NegotiationTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, указывающее максимальную длительность этапа согласования режима безопасности между сервером и клиентом.  
  
### ReconnectTransportOnFailure  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, будут ли подключения, использующие режим обмена сообщениями WS\-Reliable, пытаться восстановиться после транспортных сбоев.  
  
### ReplayCacheSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Количество кэшированных параметров nonce, используемых для определения ответов.  
  
### ReplayWindow  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое указывает срок действия параметров nonce отдельного сообщения.  
  
### SessionKeyRenewalInterval  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает интервал времени, по истечении которого инициатор обновляет ключ сеанса безопасности.  
  
### SessionKeyRolloverInterval  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает интервал времени, указывающий период, в течение которого предыдущий сеансовый ключ остается действительным для входящих сообщений, пока выполняется обновление ключа.  
  
### TimestampValidityDuration  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое определяет интервал времени, указывающий срок действия отметки времени.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>