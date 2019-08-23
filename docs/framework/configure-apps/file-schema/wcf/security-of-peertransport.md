---
title: <security> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: bdd3b236c9bae198f8027c4ca0c0fa5b70d30342
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936643"
---
# <a name="security-of-peertransport"></a>\<> безопасности > \<пиртранспорт
Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Пиртранспорт >  
\<> безопасности  
  
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
|[\<> транспорта](transport-of-peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки. Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой. Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Пиртранспорт >](peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Безопасность транспорта](../../../wcf/feature-details/transport-security.md)
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспорта](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
