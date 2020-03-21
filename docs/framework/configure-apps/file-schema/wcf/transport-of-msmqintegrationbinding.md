---
title: <transport> из <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152961"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<транспортное \<> msmqIntegration>
Определяет параметры безопасности для транспорта интеграции очереди сообщений.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceМодель>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<привязки>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationОбязательная>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<связывающая>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>безопасности**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<транспортный>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ. Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимые значения.<br /><br /> - Нет: Нет аутентификации.<br />- WindowsDomain: Механизм проверки подлинности использует Active Directory, чтобы получить сертификат X.509 для SID, связанный с сообщением. Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />- Сертификат: Канал получает сертификат из магазина сертификатов.<br /><br /> Значение по умолчанию - WindowsDomain. Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений. Допустимые значения.<br /><br /> - RC4Stream<br />- AES<br /><br /> Значение по умолчанию - RC4Stream. Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ. Шифрование обеспечивает целостность сообщений, в то время как EncryptAndSign обеспечивает целостность сообщений и неотказ; то есть, сообщение действительно исходит от отправителя и отправителя, кто они говорят, что они есть.<br /><br /> - Допустимые значения включают в себя следующее:<br />- Нет: Нет защиты.<br />- Знак: Сообщения подписаны.<br />- EncryptAndSign: Сообщения зашифрованы и подписаны.<br /><br /> Значение по умолчанию - Sign. Это атрибут типа ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|- Определяет алгоритм, который будет использоваться в вычислении дайджеста как часть подписей. Допустимые значения.<br />- MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Значение по умолчанию - SHA1. Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Из-за проблем с столкновениями с MD5 и SHA1, Microsoft рекомендует SHA256 или лучше.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<>безопасности](security-of-basichttpbinding.md)|Определяет параметры безопасности для привязки MSMQ.|  
  
## <a name="remarks"></a>Remarks  
 Данный элемент инкапсулирует параметры безопасности для транспорта интеграции очереди сообщений. Данные параметры одинаковы для интеграции очереди сообщений и использующих очереди транспортов. Это позволяет задать режим проверки подлинности, алгоритм шифрования, алгоритм SHA и уровень защиты.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<связывающая>](bindings.md)
