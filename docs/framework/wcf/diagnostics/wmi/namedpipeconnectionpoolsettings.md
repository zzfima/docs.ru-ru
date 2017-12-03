---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18740c4c87aaeafcd0a28991376e0c45fe688223
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings
NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс NamedPipeConnectionPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс NamedPipeConnectionPoolSettings имеет следующие свойства.  
  
### <a name="groupname"></a>GroupName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих соединений для каждой конечной точки на клиенте.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
