---
title: '&lt;transport&gt; для &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: c82e91543920522f0ed6232036ec1b5a94189fa8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148947"
---
# <a name="lttransportgt-of-ltpeertransportgt"></a>&lt;transport&gt; для &lt;peerTransport&gt;
Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<peerTransport >  
\<Безопасность >  
\<Транспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|credentialType|Необязательно. Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта. Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>Атрибут credentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Сертификат|Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.|  
|Пароль|Для проверки подлинности однорангового транспорта канала необходим правильный пароль.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Определяет параметры безопасности для однорангового транспорта.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент имеет значение только в том случае, если атрибуту режима [ \<безопасности >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) присваивается `Transport` или `TransportWithMessageCredential`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
