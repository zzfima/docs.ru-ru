---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124232"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
 Тип доступа: Только чтение  
  
 Настройки пула подключений.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимально допустимое количество ожидающих запросов на подключение в очереди.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
