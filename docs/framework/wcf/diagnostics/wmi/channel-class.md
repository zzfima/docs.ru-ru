---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668396"
---
# <a name="channel-class"></a>Класс Channel
Канал  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс Channel не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс Channel имеет следующие свойства.  
  
### <a name="localaddress"></a>LocalAddress  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Локальная конечная точка канала.  
  
### <a name="ref"></a>ref  
 Тип данных: Конечная точка  
  
 Тип доступа: Только чтение  
  
 Ссылка на конечную точку, к которой подключается канал.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Удаленный адрес, связанный с каналом.  
  
### <a name="sessionid"></a>SessionId  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Идентификатор текущего сеанса, если он существует.  
  
### <a name="type"></a>Тип  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Тип канала.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.ChannelBase>
