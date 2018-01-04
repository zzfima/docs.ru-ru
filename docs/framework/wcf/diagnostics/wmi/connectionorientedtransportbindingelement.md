---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0d399eb859118dfe94eb9e0a421fa405ae0f414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ConnectionOrientedTransportBindingElement не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  
 Класс ConnectionOrientedTransportBindingElement имеет следующие свойства.  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Задает интервал времени, который выделяется для инициализации канала до возникновения тайм-аута.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Размер буфера, используемого для передачи по сети фрагмента сериализованного сообщения от клиента серверу.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально используемый размер буфера.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальный промежуток времени, в течение которого фрагмент сообщения или все сообщение может оставаться в буфере перед отправкой.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число ожидающих асинхронных потоков приема, доступных для обработки входящих подключений к службе.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество ожидающих подключений.  
  
### <a name="transfermode"></a>TransferMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, следует ли буферизировать сообщения, или передавать их потоком с использованием транспорта, ориентированного на подключения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
