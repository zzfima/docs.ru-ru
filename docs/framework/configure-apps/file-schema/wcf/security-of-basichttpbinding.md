---
title: <security> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399895"
---
# <a name="security-of-basichttpbinding"></a>\<> \<безопасности BasicHttpBinding >
Определяет возможности [ \<безопасности > BasicHttpBinding](basichttpbinding.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> basicHttpBinding**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|режим|Необязательный параметр. Задает тип используемого механизма обеспечения безопасности. Значение по умолчанию — `None`. Это атрибут типа <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Атрибут mode  
  
|Значение|Описание|  
|-----------|-----------------|  
|Отсутствуют|— Сообщения не защищаются во время перемещения.|  
|Transport|Безопасность обеспечивается с помощью транспорта HTTPS. Сообщения SOAP защищаются при помощи HTTPS. Служба проходит проверку подлинности для клиента с использованием сертификата X.509. Проверка подлинности клиента осуществляется с помощью предоставленного ClientCredentialType. См. [> транспорта.\<](transport-of-basichttpbinding.md)|  
|Сообщение|Безопасность обеспечивается с помощью средств безопасности сообщений SOAP. По умолчанию текст сообщений шифруется и подписывается. Для этой привязки система требует, чтобы клиенту был предоставлен сертификат сервера с использованием внештатного канала. Единственным допустимым значением `ClientCredentialType` для данной привязки является `Certificate`.|  
|TransportWithMessageCredential|Целостность, конфиденциальность и проверка подлинности сервера обеспечиваются с помощью средств безопасности транспорта. Проверка подлинности клиента осуществляется при помощи механизма безопасности сообщений SOAP. Данный режим может использоваться, когда проверка подлинности клиента осуществляется с помощью имени пользователя/пароля и существует развернутый канал HTTP с обеспечением безопасности при передаче сообщений.|  
|TransportCredentialOnly|Данный режим не обеспечивает целостности и конфиденциальности сообщений. Он предоставляет проверку подлинности клиента на основе http. Этот режим следует использовать с осторожностью. Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> транспорта](transport-of-basichttpbinding.md)|Определяет параметры безопасности транспорта для базовой службы HTTP. Данный элемент соответствует <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<> сообщения](message-of-basichttpbinding.md)|Определяет параметры безопасности сообщений для базовой службы HTTP. Данный элемент соответствует <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|привязка|[ Элемент\<Binding > BasicHttpBinding](basichttpbinding.md).|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию сообщение SOAP не защищено и проверка подлинности клиента не выполняется. Данный элемент позволяет настроить дополнительные параметры безопасности для элемента `basicHttpBinding`.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Выбор типа учетных данных](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
