---
title: '&lt;transport&gt; для &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 1b0de5e1d581384d00c18dbefbf7b170325e2061
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43777328"
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a>&lt;transport&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности транспорта.  
  
 \<система. ServiceModel >  
\<привязки >  
\<netMsmqBinding >  
\<Привязка >  
\<Безопасность >  
\<Транспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|msmqAuthenticationMode|Задает способ проверки подлинности сообщения транспортом MSMQ. Допустимы следующие значения:<br /><br /> -None: Без проверки подлинности.<br />-WindowsDomain: Механизм проверки подлинности использует Active Directory для получения сертификата X.509 для идентификатора безопасности, связанные с данным сообщением. Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.<br />-Certificate: Канал извлекает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию — `WindowsDomain`.<br /><br /> Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимы следующие значения:<br /><br /> -RC4Stream<br />-AES<br />-Значение по умолчанию — `RC4Stream`. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqprotectionLevel|Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ. Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность. Это гарантирует, что сообщение действительно поступило от отправителя, и отправитель действительно является тем, за кого он себя выдает. Допустимы следующие значения:<br /><br /> -None: Без защиты.<br />-Sign: Сообщения подписываются.<br />-EncryptAndSign: Сообщения шифруются и подписываются.<br />-Значение по умолчанию — `Sign`.|  
|msmqSecureHashAlgorithm|Указывает алгоритм хэширования, который будет использоваться при вычислении дайджеста сообщения. Допустимы следующие значения:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Значение по умолчанию — `SHA1`. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Определяет параметры безопасности для поставленного в очередь транспорта.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки службы Windows Communication Foundation и клиентов](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
