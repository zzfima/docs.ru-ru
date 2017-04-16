---
title: "&lt;knownCertificates&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &lt;knownCertificates&gt;
Представляет коллекцию сертификатов X.509, которые предоставляются для проверки подлинности учетных данных безопасности, выданных службой маркеров безопасности \(STS\).  
  
## Синтаксис  
  
```  
  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|Добавляет сертификат X.509 в коллекцию.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|Задает маркер, выданный в качестве учетных данных службы.|  
  
## Заметки  
 В сценарии с выданным маркером имеется три этапа.  На первом этапе клиент, который пытается получить доступ к службе, направляется к *службе маркеров безопасности*.  Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language \(SAML\).  После этого клиент возвращается к службе с этим маркером.  Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.  Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 Элемент [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) является хранилищем подобных сертификатов службы маркеров безопасности.  Используйте элемент [\<knownCertificates\> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md), чтобы добавить сертификаты.  Вставьте элемент [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.  
  
```  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 По умолчанию сертификаты должны быть получены от службы маркеров безопасности.  Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.  
  
 Условия, соблюдение которых необходимо для подтверждения подлинности клиента федеративной службой, а также подробные сведения об использовании данного элемента конфигурации см. в разделе [Как настраивать учетные данные службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  Дополнительные сведения о федеративных сценариях см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Пример, в котором показано наполнение коллекции в конфигурации, см. в разделе [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).  
  
## См. также  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)   
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Как настраивать учетные данные службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)