---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс TcpTransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс TcpTransportBindingElement имеет следующие свойства.  
  
### <a name="connectionpoolsettings"></a>ConnectionPoolSettings  
 Тип данных: TcpConnectionPoolSettings  
  
 Тип доступа: только для чтения  
  
 Настройки пула подключений.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально допустимое количество ожидающих запросов на подключение в очереди.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
