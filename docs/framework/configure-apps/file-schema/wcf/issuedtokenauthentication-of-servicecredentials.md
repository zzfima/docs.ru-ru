---
title: '&lt;issuedTokenAuthentication&gt; для &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 43f03ad32345195324c9ba2a3977d294a7a2b789
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151492"
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a>&lt;issuedTokenAuthentication&gt; для &lt;serviceCredentials&gt;
Определяет пользовательский маркер, выданный в качестве учетных данных службы.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
\<issuedTokenAuthentication >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`allowedAudienceUris`|Возвращает набор целевых универсальных кодов ресурса (URI), для которых может быть предназначен маркер безопасности <xref:System.IdentityModel.Tokens.SamlSecurityToken>, чтобы считаться допустимым в экземпляре <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>. Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.|  
|`allowUntrustedRsaIssuers`|Логическое значение, которое указывает, допускаются ли недоверенные издатели сертификатов RSA.<br /><br /> Сертификаты подписываются центрами сертификации (ЦС) для проверки подлинности. Недоверенным издателем является ЦС, который не указан как надежный для подписания сертификатов.|  
|`audienceUriMode`|Возвращает значение, которое указывает, должно ли проверяться свойство <xref:System.IdentityModel.Tokens.SamlSecurityToken> маркера безопасности <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>. Это значение имеет тип <xref:System.IdentityModel.Selectors.AudienceUriMode>. Дополнительные сведения об использовании этого атрибута см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.|  
|`certificateValidationMode`|Устанавливает режим проверки сертификата. Одно из допустимых значений для <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`. Значение по умолчанию — `ChainTrust`.|  
|`customCertificateValidatorType`|Необязательная строка. Тип и сборка, используемые для проверки пользовательского типа. Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|`revocationMode`|Задает режим отзыва, который указывает, проводится ли проверка списка отозванных сертификатов; этот режим также определяет способ проверки: с подключением к сети или автономно. Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.|  
|`samlSerializer`|Необязательный строковый атрибут, который задает тип SamlSerializer, который используется для учетных данных службы. Значение по умолчанию - пустая строка.|  
|`trustedStoreLocation`|Необязательное перечисление. Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`knownCertificates`|Задает коллекцию элементов <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>, которая задает доверенных издателей для учетных данных службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Примечания  
 В сценарии с выданным маркером имеется три этапа. На первом этапе клиент, пытающийся получить доступ к службе называется *служба маркеров безопасности*. Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML). После этого клиент возвращается к службе с этим маркером. Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента. Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 Этот элемент является хранилищем подобных сертификатов службы маркеров безопасности. Чтобы добавить сертификаты, используйте [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 По умолчанию сертификаты должны быть получены от службы маркеров безопасности. Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.  
  
 Дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Практическое руководство. Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
