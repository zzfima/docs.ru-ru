---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591487"
---
# <a name="channelpoolsettings"></a>ChannelPoolSettings
ChannelPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
 Тип доступа: Только чтение  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Максимальное время ожидания завершения операции аренды.  
  
### <a name="maxoutboundchannelsperendpoint"></a>MaxOutboundChannelsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное число исходящих каналов для каждой конечной точки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
