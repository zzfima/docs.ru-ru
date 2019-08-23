---
title: <transport> из <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 265b68e058919d1d5c5f1dbcfb1419b57be9aeab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915550"
---
# <a name="transport-of-nettcpbinding"></a>\<transport>  — \<netTcpBinding>
Определяет тип требований безопасности на уровне сообщений для конечной точки, [ \<](nettcpbinding.md)настроенной с помощью > NetTcpBinding.  
  
 \<системой. > ServiceModel  
\<привязки >  
\<netTcpBinding >  
\<Привязка >  
\<> безопасности  
\<> транспорта  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|clientCredentialType|Необязательный параметр. Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.<br /><br /> — Значение по умолчанию `Windows`—.<br />— Этот атрибут имеет тип <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Необязательный параметр. Определяет безопасность на уровне транспорта TCP. Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче. Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.<br /><br /> Значение по умолчанию — `EncryptAndSign`.|  
|sslProtocols|Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются. Значение по умолчанию&#124;—&#124;TLS Tls11 Tls12.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never - политика никогда не применяется (расширенная защита отключена).<br />2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always - политика применяется всегда. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Отсутствуют|Анонимный клиент. Это требует сертификата для службы.|  
|Windows|Задает проверку подлинности Windows для клиента с использованием согласования SP (согласование Kerberos).|  
|Сертификат|Проверка подлинности клиента выполняется с использованием сертификата. Это требует согласования SSL и сертификата для службы.|  
  
## <a name="protectionlevel-attribute"></a>Атрибут protectionLevel  
  
|Значение|Описание|  
|-----------|-----------------|  
|Отсутствуют|Нет защиты.|  
|Sign|Сообщения подписываются.|  
|EncryptAndSign|— Сообщения шифруются и подписываются.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-nettcpbinding.md)|Указывает возможности [ \<безопасности > NetTcpBinding](nettcpbinding.md).|  
  
## <a name="remarks"></a>Примечания  
 Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности. Если этот режим безопасности выбран для какой-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows (Negotiate) или SSL по TCP.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
