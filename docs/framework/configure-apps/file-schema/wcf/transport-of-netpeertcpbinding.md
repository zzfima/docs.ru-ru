---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915564"
---
# <a name="transport-of-netpeertcpbinding"></a>\<транспортное \<> из netPeerTcpBinding >
Задает параметры безопасности на транспортном уровне при использовании [ \<> netPeerTcpBinding](netpeertcpbinding.md).  
  
 \<системой. > ServiceModel  
\<привязки >  
\<netPeerTcpBinding >  
\<Привязка >  
\<> безопасности  
\<> транспорта  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|credentialType|Необязательный параметр. Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта. Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Атрибут credentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Сертификат|Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.|  
|Пароль|Для проверки подлинности однорангового транспорта канала необходим правильный пароль.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-netpeerbinding.md)|Определяет параметры безопасности для [ \<> netPeerTcpBinding](netpeertcpbinding.md).|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
