---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48364c2bcfa50476ac5f9f00f87c17f97dc14017
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс PeerTransportBindingElement не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  
 Класс PeerTransportBindingElement имеет следующие свойства.  
  
### <a name="listenipaddress"></a>ListenIPAddress  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 IP-адрес, на котором одноранговый узел будет ожидать сообщения.  
  
### <a name="port"></a>Порт  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.  
  
### <a name="security"></a>Безопасность  
 Тип данных: PeerSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Параметры безопасности однорангового транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
