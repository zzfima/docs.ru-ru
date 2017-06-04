---
title: "&lt;add&gt; для &lt;knownCertificates&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;add&gt; для &lt;knownCertificates&gt;
Добавляет сертификат X.509 в коллекцию известных сертификатов.  
  
## Синтаксис  
  
```  
  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|findValue|Строка.  Значение, которое нужно найти.|  
|storeLocation|Перечисление.  Одно из двух местоположений хранилища, где следует проводить поиск.|  
|storeName|Перечисление.  Одно из системных хранилищ, где следует проводить поиск.|  
|x509FindType|Перечисление.  Одно из полей сертификата, где следует проводить поиск.|  
  
## Атрибут findValue  
  
|Значение|Описание|  
|--------------|--------------|  
|Строковое|Значение зависит от поля \(заданного атрибутом x509FindType\), поиск которого выполняется.  Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.|  
  
## Атрибут x509FindType  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|К числу значений относятся следующие: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## Атрибут storeLocation  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|CurrentUser или LocalMachine.|  
  
## Атрибут storeName  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|К числу значений относятся следующие: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople и TrustedPublisher.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.|  
  
## Заметки  
 В сценарии с выданным маркером имеется три этапа.  На первом этапе клиент, который пытается получить доступ к службе, направляется к *службе маркеров безопасности*.  Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language \(SAML\).  После этого клиент возвращается к службе с этим маркером.  Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.  Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 Элемент [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) является хранилищем подобных сертификатов службы маркеров безопасности.  Используйте элемент [\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md), чтобы добавить сертификаты.  Вставьте элемент [\<add\> element \<knownCertificates\> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.  
  
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
  
## Пример  
 В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## См. также  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>   
 [\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Как настраивать учетные данные службы федерации](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)