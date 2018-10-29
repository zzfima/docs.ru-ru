---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50047375"
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
  
 Тип доступа: только для чтения  
  
 Локальная конечная точка канала.  
  
### <a name="ref"></a>ref  
 Тип данных: Endpoint  
  
 Тип доступа: только для чтения  
  
 Ссылка на конечную точку, к которой подключается канал.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Удаленный адрес, связанный с каналом.  
  
### <a name="sessionid"></a>SessionId  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Идентификатор текущего сеанса, если он существует.  
  
### <a name="type"></a>Тип  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип канала.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.ChannelBase>
