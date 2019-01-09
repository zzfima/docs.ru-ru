---
title: '&lt;transport&gt; для &lt;netTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 8416701ce4e787a49ee0a4bdd4829c6592cde94c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147334"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a>&lt;transport&gt; для &lt;netTcpBinding&gt;
Определяет тип требований безопасности уровня сообщений для конечной точки, настроенной с [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 \<система. ServiceModel >  
\<привязки >  
\<netTcpBinding >  
\<Привязка >  
\<Безопасность >  
\<Транспорт >  
  
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
|clientCredentialType|Необязательно. Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности транспорта.<br /><br /> -Значение по умолчанию — `Windows`.<br />— Этот атрибут имеет тип <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Необязательно. Определяет безопасность на уровне транспорта TCP. Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче. Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.<br /><br /> Значение по умолчанию — `EncryptAndSign`.|  
|sslProtocols|Значение флага перечисления SslProtocols, указывающее, какие протоколы SslProtocols поддерживаются. По умолчанию используется Tls&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.<br /><br /> 1.  Never - политика никогда не применяется (расширенная защита отключена).<br />2.  WhenSupported - политика применяется только тогда, когда клиент поддерживает расширенную защиту.<br />3.  Always - политика применяется всегда. Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Анонимный клиент. Это требует сертификата для службы.|  
|Windows|Задает проверку подлинности Windows для клиента с использованием согласования SP (согласование Kerberos).|  
|Сертификат|Проверка подлинности клиента выполняется с использованием сертификата. Это требует согласования SSL и сертификата для службы.|  
  
## <a name="protectionlevel-attribute"></a>Атрибут protectionLevel  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Нет защиты.|  
|Sign|Сообщения подписываются.|  
|EncryptAndSign|-Сообщения шифруются и подписываются.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Задает возможности безопасности [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## <a name="remarks"></a>Примечания  
 Безопасность транспорта используется для обеспечения целостности и конфиденциальности сообщений SOAP и для взаимной проверки подлинности. Если этот режим безопасности выбран для какой-либо привязки, стек каналов настраивается с использованием безопасного транспорта, а сообщения SOAP защищаются с использованием безопасности транспорта, например Windows (Negotiate) или SSL по TCP.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
