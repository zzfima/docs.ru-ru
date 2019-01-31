---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 4c1dc15621138aa692f0a30d285f729c2bd670d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274122"
---
# <a name="knowncertificates"></a>\<knownCertificates >
Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
\<issuedTokenAuthentication>  
\<knownCertificates >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|Добавляет сертификат X.509 в коллекцию.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|Задает маркер, выданный в качестве учетных данных службы.|  
  
## <a name="remarks"></a>Примечания  
 В сценарии с выданным маркером имеется три этапа. На первом этапе клиент, пытающийся получить доступ к службе называется *служба маркеров безопасности*. Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML). После этого клиент возвращается к службе с этим маркером. Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента. Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 [ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент является хранилищем подобных сертификатов службы маркеров безопасности. Чтобы добавить сертификаты, используйте [ \<knownCertificates > элемент](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Вставить [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.  
  
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
  
 Необходимые условия для клиента не может проверить подлинность федеративной службы, а также дополнительные сведения об использовании данного элемента конфигурации см. в разделе [как: Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md). Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Пример, показывающий, как для заполнения коллекции в конфигурации, см. в разделе [ \<Добавить >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Настройка учетных данных службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
