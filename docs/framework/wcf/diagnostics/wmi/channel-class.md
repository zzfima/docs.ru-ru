---
title: "Класс Channel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1df634a61cce695fca74fdfe53beea6c0f83d082
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
