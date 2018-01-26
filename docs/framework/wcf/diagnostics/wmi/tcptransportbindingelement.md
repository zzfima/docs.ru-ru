---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e230cbccee211fbda219000fbbd2cda5275776b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
