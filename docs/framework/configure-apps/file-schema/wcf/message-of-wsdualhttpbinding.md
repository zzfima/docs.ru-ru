---
title: <message> из <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 75101744-eed8-4d61-91f4-5fc4473a21f2
ms.openlocfilehash: 796c6bf5df541e525624a609fcfba255eda673cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931479"
---
# <a name="message-of-wsdualhttpbinding"></a>\<> сообщений > \<WSDualHttpBinding
Определяет безопасность на [ \<](wsdualhttpbinding.md)уровне сообщений для > WSDualHttpBinding.  
  
 \<системой. > ServiceModel  
\<привязки >  
\<wsDualHttpBinding >  
\<Привязка >  
\<> безопасности  
\<> сообщения  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
         negotiateServiceCredential="Boolean"
         algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
</message>
```  
  
## <a name="type"></a>Тип  
 <xref:System.ServiceModel.MessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|algorithmSuite|Необязательный параметр. Задает алгоритмы шифрования сообщений и ключей. Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).<br /><br /> Возможные значения приводятся ниже. Значение по умолчанию — `Basic256`.|  
|clientCredentialType|Необязательный параметр. Задает тип учетных данных, которые должны использоваться при проверке подлинности клиента с помощью режима безопасности `Message`. Возможные значения приводятся ниже. Значение по умолчанию — `Windows`.<br /><br /> Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.|  
|negotiateServiceCredential|Необязательный параметр. Логическое значение, которое указывает, предоставляются ли учетные данные службы клиенту по внештатному каналу, или же клиент получает их от службы в процессе согласования. Подобное согласование происходит перед обычным обменом сообщениями.<br /><br /> Если атрибут равен None, username или Certificate, установка этого `false` атрибута подразумевает, что сертификат службы доступен на клиентском аппаратном контроллере, а клиент должен указать сертификат службы (с помощью `clientCredentialType` serviceCertificate >) в [ поведениислужбыServiceCredentials>.\<](servicecertificate-of-servicecredentials.md) [ \<](servicecredentials.md) Данный режим совместим со стеками SOAP, которые реализуют WS-Trust и WS-SecureConversation.<br /><br /> Если атрибут `ClientCredentialType` имеет значение `Windows`, то установка для данного атрибута значения `false` задает проверку подлинности на основе Kerberos. Это означает, что клиент и служба должны относиться к одному домену Kerberos. Данный режим совместим со стеками SOAP, которые реализуют профиль маркера Kerberos (в соответствии с определением в OASIS WSS TC), а также WS-Trust и WS-SecureConversation. Когда данный атрибут равен `true`, то происходит согласование .NET SOAP, при котором обмен SPNego производится при помощи сообщений SOAP.<br /><br /> Значение по умолчанию — `true`.|  
  
## <a name="algorithmsuite-attribute"></a>Атрибут algorithmSuite  
  
|Значение|Описание|  
|-----------|-----------------|  
|Basic128|Используется шифрование Aes128, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic192|Используется шифрование Aes192, Sha1 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256|Используется шифрование Aes256, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256Rsa15|Используется Aes256 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.|  
|Basic192Rsa15|Используется Aes192 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.|  
|TripleDes|Используется шифрование TripleDes, Sha1 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic128Rsa15|Используется Aes128 для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.|  
|TripleDesRsa15|Используется TripleDes для шифрования сообщения, Sha1 для хэш-кода и Rsa15 для шифрования ключа.|  
|Basic128Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic192Sha256|Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic256Sha256|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa-oaep-mgf1p для шифрования ключа.|  
|TripleDesSha256|Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa-oaep-mgf1p для шифрования ключа.|  
|Basic128Sha256Rsa15|Используется Aes128 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.|  
|Basic192Sha256Rsa15|Используется Aes192 для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.|  
|Basic256Sha256Rsa15|Используется Aes256 для шифрования сообщения, Sha256 для хэша и Rsa15 для шифрования ключа.|  
|TripleDesSha256Rsa15|Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Отсутствуют|Данный атрибут позволяет службе взаимодействовать с анонимными клиентами. Для службы это означает, что она не требует учетных данных клиента. Для клиента это означает, что он не должен предоставлять никаких учетных данных.|  
|Windows|Атрибут позволяет проводить обмен сообщениями SOAP, если выполнена проверка подлинности с помощью учетных данных Windows. Если атрибут `negotiateServiceCredential` имеет значение `true`, то происходит согласование SSPI или используется Kerberos (совместимый стандарт).|  
|UserName|Позволяет службе запрашивать проверку подлинности клиента на основе учетных данных типа UserName. WCF не поддерживает отправку дайджеста пароля или получение ключей с помощью пароля и использование таких ключей для обеспечения безопасности сообщений. Таким образом, WCF обеспечивает защиту транспорта при использовании учетных данных пользователя. Результатом использования такого режима работы с учетными данными является либо обмен с возможностью взаимодействия, либо согласование без возможности взаимодействия в зависимости от атрибута `negotiateServiceCredential`.|  
|Сертификат|Позволяет службе требовать проверки подлинности клиента с помощью сертификата. Если используется режим безопасности сообщений и атрибут `negotiateServiceCredential` имеет значение `false`, то клиенту должен быть предоставлен сертификат службы.|  
|IssuedToken|Задает пользовательский маркер, который обычно выдается службой маркеров безопасности.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-wsdualhttpbinding.md)|Определяет возможности [ \<безопасности > WSDualHttpBinding](wsdualhttpbinding.md).|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSDualHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>
- <xref:System.ServiceModel.MessageSecurityOverHttp>
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../misc/binding.md)
