---
title: Элемент &lt;message&gt; &lt;ws2007FederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 278464503b5576b5562de58a7cb3350aad9faa7a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145956"
---
# <a name="ltmessagegt-element-of-ltws2007federationhttpbindinggt"></a>Элемент &lt;message&gt; &lt;ws2007FederationHttpBinding&gt;
Определяет параметры безопасности уровня сообщений для [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элемент.  
  
 \<система. ServiceModel >  
\<привязки >  
\<ws2007FederationHttpBinding >  
\<Привязка >  
\<Безопасность >  
\<сообщение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`algorithmSuite`|Необязательно. Задает алгоритмы шифрования сообщений, сигнатуры и ключей. Алгоритмы и размеры ключей определяются классом <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).<br /><br /> В следующей таблице приводятся возможные значения. Значение по умолчанию - Basic256.|  
|`issuedKeyType`|Задает тип выдаваемого ключа. Допустимы следующие значения:<br /><br /> -SymmetricKey<br />-PublicKey<br />-BearerKey<br /><br /> Значение по умолчанию - SymmetricKey. Это атрибут типа <xref:System.IdentityModel.Tokens.SecurityKeyType>.|  
|`issuedTokenType`|Универсальный код ресурса (URI), который задает тип выдаваемых маркеров. Значение по умолчанию — `null`.|  
|`negotiateServiceCredential`|Значение, которое определяет, должен ли проводиться обмен учетными данными службы в рамках процесса согласования, или эти данные доступны вне диапазона. Значением по умолчанию является `true`, означающее, что учетные данные службы согласуются.|  
  
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
|TripleDesSha256Rsa15|Используется TripleDes для шифрования сообщения, Sha256 для хэш-кода и Rsa15 для шифрования ключа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<claimTypeRequirements >](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|Задает коллекцию типов утверждений для этой привязки. Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.|  
|[\<issuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Задает конечную точку, которая выдает маркер безопасности. Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.|  
|[\<issuerMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Задает адрес конечной точки издателя.|  
|[\<tokenRequestParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|Коллекция параметров запроса маркера. Каждый параметр представляет собой элемент XML.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|Определяет параметры безопасности для привязки.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 `System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
