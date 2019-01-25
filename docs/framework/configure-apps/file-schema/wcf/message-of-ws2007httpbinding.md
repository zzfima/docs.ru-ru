---
title: '&lt;message&gt; для &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
ms.openlocfilehash: 6a6010399d0dd884e5c921829395531f1133e439
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677619"
---
# <a name="ltmessagegt-of-ltws2007httpbindinggt"></a>&lt;message&gt; для &lt;ws2007HttpBinding&gt;
Определяет параметры безопасности уровня сообщений для [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемент.  
  
 \<system.ServiceModel>  
\<привязки >  
\<ws2007HttpBinding >  
\<Привязка >  
\<Безопасность >  
\<сообщение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ws2007HttpBinding>
  <binding>
    <security>
      <message clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Enumeration. See algorithmSuite Attribute below."
               defaultProtectionLevel="None/Sign/EncryptionAndSign" />
    </security>
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="type"></a>Тип  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`algorithmSuite`|Задает алгоритмы шифрования сообщений и ключей. Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).<br /><br /> Значение по умолчанию - Basic256.|  
|`clientCredentialType`|Необязательно. Задает тип учетных данных, используемых при проверке подлинности клиента с помощью режима безопасности, может принимать значения `Message` или `TransportWithMessageCredentials`. См. значения перечисления в следующей таблице. По умолчанию используется Windows.<br /><br /> Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.|  
|`establishSecurityContext`|Значение, которое определяет, будет ли защищенный канал устанавливать защищенную сессию. Защищенная сессия перед тем, как обмениваться сообщениями приложения, устанавливает маркер контекста безопасности (SCT). После установки этого маркера защищенный канал предлагает вышестоящим каналам интерфейс <xref:System.ServiceModel.Channels.ISession>. Дополнительные сведения об использовании защищенных сеансов см. в разделе [как: Создание сеанса безопасности](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> Значение по умолчанию — `true`.|  
|`negotiateServiceCredential`|Необязательно. Значение, которое определяет, предоставляются учетные данные службы клиенту по внештатному каналу, или же клиент получает их от службы в процессе согласования. Подобное согласование происходит перед обычным обменом сообщениями.<br /><br /> Если `clientCredentialType` атрибут имеет значение None, Username или Certificate, установка для данного атрибута `false` подразумевает, что сертификат службы доступен в клиенте по внештатному каналу и клиент должен указать сертификат службы (с помощью [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) в [ \<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) поведение службы. Данный режим несовместим со стеками SOAP, которые реализуют WS-Trust и WS-SecureConversation.<br /><br /> Если атрибут `ClientCredentialType` имеет значение `Windows`, то установка для данного атрибута значения `false` задает проверку подлинности на основе Kerberos. Это означает, что клиент и служба должны относиться к одному домену Kerberos. Данный режим совместим со стеками SOAP, которые реализуют профиль маркера Kerberos (который определен в OASIS WSS TC), а также WS-Trust и WS-SecureConversation.<br /><br /> Когда данный атрибут равен `true`, то в этом случае выполняется согласование .NET SOAP, при котором обмен <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> производится посредством сообщений SOAP.<br /><br /> Значение по умолчанию — `true`.|  
  
## <a name="algorithmsuite-attribute"></a>Атрибут algorithmSuite  
  
|Значение|Описание|  
|-----------|-----------------|  
|Basic128|Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic192|Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256|Используется шифрование Aes256, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256Rsa15|Используется Aes256 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|Basic192Rsa15|Используется Aes192 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|TripleDes|Используется шифрование TripleDes, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic128Rsa15|Используется Aes128 для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|TripleDesRsa15|Используется TripleDes для шифрования сообщения, Sha1 для хэша и Rsa15 для шифрования ключа.|  
|Basic128Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic192Sha256|Используется Aes192 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|TripleDesSha256|Используется TripleDes для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic128Sha256Rsa15|Используется Aes128 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|Basic192Sha256Rsa15|Используется Aes192 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|Basic256Sha256Rsa15|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|TripleDesSha256Rsa15|Используется TripleDes для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|`None`|Данный атрибут позволяет службе взаимодействовать с анонимными клиентами. Для службы это означает, что она не требует учетных данных клиента. Для клиента это означает, что он не должен предоставлять никаких учетных данных.|  
|`Certificate`|Позволяет службе требовать проверки подлинности клиента с помощью сертификата. Если используется режим безопасности `message` и атрибут `negotiateServiceCredential` имеет значение `false`, то клиенту должен быть предоставлен сертификат службы.|  
|`IssuedToken`|Задает пользовательский маркер, который обычно выдается службой маркеров безопасности (STS).|  
|`UserName`|Позволяет службе требовать проверки подлинности клиента с помощью учетных данных `UserName`. WCF не поддерживает передачу хэш-кода пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений. Таким образом, WCF обеспечивает безопасность транспорта при использовании `UserName` учетные данные. Результатом использования такого режима работы с учетными данными является либо обмен с возможностью взаимодействия, либо согласование без возможности взаимодействия в зависимости от атрибута `negotiateServiceCredential`.|  
|`Windows`|Атрибут позволяет проводить обмен сообщениями SOAP, если выполнена проверка подлинности с помощью учетных данных `Windows`. Если атрибут `negotiateServiceCredential` имеет значение `true`, то происходит согласование SSPI, или используется Kerberos (совместимый стандарт).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Определяет параметры безопасности для [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../../../docs/framework/misc/binding.md)
