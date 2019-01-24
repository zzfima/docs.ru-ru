---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 4e89dbe35a5232c612555b273c3d771aad42aeb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584809"
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings
TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс TcpConnectionPoolSettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс TcpConnectionPoolSettings имеет следующие свойства.  
  
### <a name="groupname"></a>GroupName  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Максимальное время ожидания завершения выполнения операции аренды.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное число исходящих подключений для каждой конечной точки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
