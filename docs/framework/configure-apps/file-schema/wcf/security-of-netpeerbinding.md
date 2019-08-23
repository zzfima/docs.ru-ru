---
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936629"
---
# <a name="security-of-netpeerbinding"></a>\<> безопасности > \<нетпирбиндинг
Определяет параметры [ \<безопасности > netPeerTcpBinding](netpeertcpbinding.md), включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.  
  
 \<системой. > ServiceModel  
\<привязки >  
\<Нетпирбиндинг >  
\<Привязка >  
\<> безопасности  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|режим|Необязательный параметр. Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки. Значение по умолчанию — `Message`. Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Атрибут mode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Сообщение|Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.|  
|Отсутствуют|Режим безопасности отключен.|  
|Transport|Безопасность обеспечивается с помощью протокола HTTPS.|  
|TransportWithMessageCredential|HTTPS обеспечивает конфиденциальность и проверку подлинности. Сообщения SOAP предоставляют различные типы учетных данных.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> транспорта](transport-of-netpeertcpbinding.md)|Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../misc/binding.md)|Определяет все возможности [ \<привязки > netPeerTcpBinding](netpeertcpbinding.md).|  
  
## <a name="remarks"></a>Примечания  
 Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Выбор типа учетных данных](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
