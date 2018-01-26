---
title: LocalServiceSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f4cc5d0676ef397f67bd9d16b2b19c6f3ee2d57e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="methods"></a>Методы  
 Класс LocalServiceSecuritySettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс LocalServiceSecuritySettings имеет следующие свойства.  
  
### <a name="detectreplays"></a>DetectReplays  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, показывающее, будут ли атаки с повторением обнаружены и ликвидированы на канале автоматически.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих безопасных сеансов, поддерживаемое службой.  
  
### <a name="issuedcookielifetime"></a>IssuedCookieLifetime  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает время существования для всех новых файлов безопасности cookie.  
  
### <a name="maxcachedcookies"></a>MaxCachedCookies  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество файлов cookie, которые могут быть кэшированы.  
  
### <a name="maxclockskew"></a>MaxClockSkew  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, указывающее максимальный разброс времени между системными часами взаимодействующих сторон.  
  
### <a name="maxpendingsessions"></a>MaxPendingSessions  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих подключений к службе.  
  
### <a name="maxstatefulnegotiations"></a>MaxStatefulNegotiations  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Количество одновременно выполняемых согласований режима безопасности.  
  
### <a name="negotiationtimeout"></a>NegotiationTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, указывающее максимальную длительность этапа согласования режима безопасности между сервером и клиентом.  
  
### <a name="reconnecttransportonfailure"></a>ReconnectTransportOnFailure  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, будут ли подключения, использующие режим обмена сообщениями WS-Reliable, пытаться восстановиться после транспортных сбоев.  
  
### <a name="replaycachesize"></a>ReplayCacheSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Количество кэшированных параметров nonce, используемых для определения ответов.  
  
### <a name="replaywindow"></a>ReplayWindow  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое указывает срок действия параметров nonce отдельного сообщения.  
  
### <a name="sessionkeyrenewalinterval"></a>SessionKeyRenewalInterval  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает интервал времени, по истечении которого инициатор обновляет ключ сеанса безопасности.  
  
### <a name="sessionkeyrolloverinterval"></a>SessionKeyRolloverInterval  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое задает интервал времени, указывающий период, в течение которого предыдущий сеансовый ключ остается действительным для входящих сообщений, пока выполняется обновление ключа.  
  
### <a name="timestampvalidityduration"></a>TimestampValidityDuration  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение типа TimeSpan, которое определяет интервал времени, указывающий срок действия отметки времени.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
