---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153013"
---
# <a name="msmqtransportsecurity"></a>\<msmqTransportSecurity>
Задает параметры безопасности транспорта MSMQ для пользовательской привязки.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceМодель>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<привязки>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<обычайОбязательный>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<связывающая>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqИнтеграция>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ. Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимые значения.<br /><br /> - Нет: Нет аутентификации.<br />- Windows: Механизм проверки подлинности использует Active Directory, чтобы получить сертификат X.509 для SID, связанный с сообщением. Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />- Сертификат: Канал получает сертификат из магазина сертификатов.<br /><br /> Значение по умолчанию - Windows. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимые значения.<br /><br /> - RC4Stream<br />- AES<br /><br /> Значение по умолчанию - RC4Stream. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ. Шифрование обеспечивает целостность сообщений, в то время как EncryptAndSign обеспечивает целостность сообщений и неотказ; то есть, сообщение действительно исходит от отправителя и отправителя, кто они говорят, что они есть. Допустимые значения.<br /><br /> - Нет: Нет защиты.<br />- Знак: Сообщения подписаны.<br />- EncryptAndSign: Сообщения зашифрованы и подписаны.<br /><br /> Значение по умолчанию - Sign. Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Задает алгоритм, который должен использоваться при вычислении хэш-кода как части сигнатур. Допустимые значения.<br /><br /> - MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Значение по умолчанию - SHA1. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с столкновениями с MD5 и SHA1, Microsoft рекомендует SHA256 или лучше.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<msmqИнтеграция>](msmqintegration.md)|Задает параметры, необходимые для взаимодействия с отправителем или получателем очереди сообщений (MSMQ).|  
|[\<msmqTransport>](msmqtransport.md)|Задает свойства обмена данными в очереди для службы Windows Communication Foundation (WCF), использующей собственный протокол MSMQ.|  
  
## <a name="remarks"></a>Remarks  
 Для получения дополнительной информации о транспортной [безопасности,](../../../wcf/feature-details/transport-security.md)см Транспортная безопасность .  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспортов](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<обычайОбязательный>](custombinding.md)
- [Транспортная безопасность](../../../wcf/feature-details/transport-security.md)
