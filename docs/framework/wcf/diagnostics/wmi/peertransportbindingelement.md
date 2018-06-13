---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 68e6a25e4e3f47c556363e2fd5aa8d3bb9946449
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485649"
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
