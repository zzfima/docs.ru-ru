---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963219"
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings
NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
 Тип доступа: Только чтение  
  
 Имя группы пула подключений, используемого элементом привязки.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Максимальное время, в течение которого подключение может простаивать перед отключением.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное число исходящих соединений для каждой конечной точки на клиенте.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
