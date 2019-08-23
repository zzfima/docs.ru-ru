---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 1210e6282a7dd6c40198693d4948a89efe841d59
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913530"
---
# <a name="knowncertificates"></a>\<Кновнцертификатес >
Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности (STS).  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceCredentials >  
\<Иссуедтокенаусентикатион >  
\<Кновнцертификатес >  
  
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
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|Добавляет сертификат X.509 в коллекцию.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Иссуедтокенаусентикатион >](issuedtokenauthentication-of-servicecredentials.md)|Задает маркер, выданный в качестве учетных данных службы.|  
  
## <a name="remarks"></a>Примечания  
 В сценарии с выданным маркером имеется три этапа. На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*. Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML). После этого клиент возвращается к службе с этим маркером. Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента. Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 Элемент [иссуедтокенаусентикатион > — это репозиторий для любых таких сертификатов службы безопасных маркеров. \<](issuedtokenauthentication-of-servicecredentials.md) Чтобы добавить сертификаты, используйте [ \<элемент кновнцертификатес >](knowncertificates.md). Вставьте > добавления для каждого сертификата, как показано в следующем примере. [ \<](add-of-knowncertificates.md)  
  
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
  
 Чтобы просмотреть условия, необходимые для проверки подлинности клиента в Федеративной службе, а также дополнительные сведения об использовании этого элемента конфигурации, см. раздел [как Настройте учетные данные на](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)служба Федерации. Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).  
  
 Пример, демонстрирующий заполнение коллекции в конфигурации, см. в разделе [ \<Add >](add-of-knowncertificates.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<Иссуедтокенаусентикатион >](issuedtokenauthentication-of-servicecredentials.md)
- [Поведения безопасности](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Практическое руководство. Настройка учетных данных на служба федерации](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
