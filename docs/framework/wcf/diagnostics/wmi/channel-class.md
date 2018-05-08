---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 4b7c66560c0c136a258c527d8a681d491eb50aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="channel-class"></a>Класс Channel
Канал  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
