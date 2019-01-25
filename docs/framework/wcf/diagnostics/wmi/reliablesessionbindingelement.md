---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: adf7d8958e2361d6e26576f6b20321b9c5666d1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688887"
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ReliableSessionBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ReliableSessionBindingElement имеет следующие свойства.  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Промежуток времени, в течение которого пункт назначения ожидает перед отправкой подтверждения источнику сообщения по надежным каналам, созданным фабрикой.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, включено ли управление потоком.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Максимальное время, в течение которого канал позволяет другому участнику соединения не отправлять никаких сообщений, прежде чем канал будет закрыт с ошибкой.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное число каналов, ожидающих принятия на прослушивателе.  
  
### <a name="maxretrycount"></a>MaxRetryCount  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное количество попыток повторной передачи надежным каналом сообщения, для которого не было получено подтверждение приема. Повторная передача осуществляется посредством вызова метода `Send` в базовом канале.  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальный размер окна передачи для надежного сеанса.  
  
### <a name="ordered"></a>Ordered  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, определяющее, прибывают ли сообщения точно в том порядке, в котором они были отправлены.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion  
 Тип данных: integer  
  
 Тип доступа: Только чтение  
  
 Целочисленное значение, задающее версию используемого в надежном канале протокола WS-ReliableMessaging.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
