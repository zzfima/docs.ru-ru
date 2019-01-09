---
title: '&lt;security&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: ec164fa8830321f90f824f85841a379d577ab5af
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147802"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a>&lt;security&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности для привязки MSMQ. Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.  
  
 \<система. ServiceModel >  
\<привязки >  
\<netMsmqBinding >  
\<Привязка >  
\<Безопасность >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|режим|Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности. Допустимы следующие значения:<br /><br /> -None: Режим безопасности отключен.<br />-Транспорта: Защита и проверка подлинности предоставляются транспортом. Это значение связано с безопасностью сообщений между двумя диспетчерами очереди. Между приложением и диспетчером очереди безопасность сообщений не обеспечивается. Существующие Msmq-приложения функционально равноценны такому режиму безопасности.<br />-Сообщение об ошибке: Указывает приложения конечными пунктами. Безопасность на транспортном уровне не предоставляется. Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.<br />-Оба: Обеспечивает безопасность на уровне сообщений SOAP и транспорта. На обоих уровнях требуются одни и те же учетные данные.<br /><br /> Значение по умолчанию - Transport. Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<сообщение >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|Определяет параметры безопасности сообщений SOAP. Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<Транспорт >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|Определяет параметры безопасности для транспорта MSMQ. Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|привязка|Элемент привязки [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)  
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
