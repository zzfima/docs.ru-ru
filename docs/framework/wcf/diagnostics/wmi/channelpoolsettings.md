---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a>ChannelPoolSettings
ChannelPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ChannelPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ChannelPoolSettings имеет следующие свойства.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Максимальное время ожидания завершения операции аренды.  
  
### <a name="maxoutboundchannelsperendpoint"></a>MaxOutboundChannelsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное число исходящих каналов для каждой конечной точки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
