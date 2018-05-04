---
title: '&lt;security&gt; для &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 9d77c250b4843c9a0f83247cae5c2859429cf5bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; для &lt;peerTransport&gt;
Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<peerTransport >  
\<Безопасность >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`mode`|Задает тип применяемого механизма обеспечения безопасности. Значение по умолчанию - Message. Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Атрибут mode  
  
|Значение|Описание|  
|-----------|-----------------|  
|`None`|Режим безопасности отключен.|  
|`Transport`|Безопасность обеспечивается с помощью протокола HTTPS.|  
|`Message`|Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.|  
|`TransportWithMessageCredential`|HTTPS обеспечивает конфиденциальность и проверку подлинности. Сообщения SOAP предоставляют различные типы учетных данных.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Транспорт >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки. Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой. Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<peerTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
