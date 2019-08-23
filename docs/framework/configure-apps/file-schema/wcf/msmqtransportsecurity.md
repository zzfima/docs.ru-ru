---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5a7dcac4edce75029bb2e0293461557f56e3c3be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933222"
---
# <a name="msmqtransportsecurity"></a>\<Свойство MsmqTransportSecurity >
Задает параметры безопасности транспорта MSMQ для пользовательской привязки.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<msmqIntegration>  
\<Свойство MsmqTransportSecurity >  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ. Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимы следующие значения:<br /><br /> None Без проверки подлинности.<br />Windows Механизм проверки подлинности использует Active Directory для получения сертификата X. 509 для идентификатора безопасности, связанного с сообщением. Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />Certificate Канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию - Windows. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимы следующие значения:<br /><br /> - RC4Stream<br />— AES<br /><br /> Значение по умолчанию - RC4Stream. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ. Шифрование обеспечивает целостность сообщения, а EncryptAndSign - целостность и неотрекаемость сообщения; то есть гарантируется, что сообщение на самом деле поступает от отправителя, и отправитель действительно является тем, кем называет себя. Допустимы следующие значения:<br /><br /> None Нет защиты.<br />Писать Сообщения подписываются.<br />EncryptAndSign Сообщения шифруются и подписываются.<br /><br /> Значение по умолчанию - Sign. Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Задает алгоритм, который должен использоваться при вычислении хэш-кода как части сигнатур. Допустимы следующие значения:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Значение по умолчанию - SHA1. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с MD5 и SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Мсмкинтегратион >](msmqintegration.md)|Задает параметры, необходимые для взаимодействия с отправителем или получателем очереди сообщений (MSMQ).|  
|[\<Мсмктранспорт >](msmqtransport.md)|Задает свойства обмена данными в очереди для службы Windows Communication Foundation (WCF), использующей собственный протокол MSMQ.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о безопасности транспорта см. в разделе [Безопасность транспорта](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспорта](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
- [Безопасность транспорта](../../../wcf/feature-details/transport-security.md)
