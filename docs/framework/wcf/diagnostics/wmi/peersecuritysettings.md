---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193166"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс PeerSecuritySettings не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс PeerSecuritySettings имеет следующие свойства.  
  
### <a name="mode"></a>Режим  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.  
  
### <a name="transport"></a>Transport  
 Тип данных: PeerTransportSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Параметры безопасности транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.PeerSecuritySettings>
