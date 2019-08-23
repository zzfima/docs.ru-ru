---
title: <add> из <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 939718e8dacca2698b6f71a3bdc1262a5dc3ee20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926682"
---
# <a name="add-of-knowncertificates"></a>\<Добавление > \<> кновнцертификатес
Добавляет сертификат X.509 в коллекцию известных сертификатов.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<serviceCredentials >  
\<Иссуедтокенаусентикатион >  
\<Кновнцертификатес >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|findValue|Строка. Значение, которое нужно найти.|  
|storeLocation|Перечисление. Одно из двух местоположений хранилища, где следует проводить поиск.|  
|storeName|Перечисление. Одно из системных хранилищ, где следует проводить поиск.|  
|x509FindType|Перечисление. Одно из полей сертификата, где следует проводить поиск.|  
  
## <a name="findvalue-attribute"></a>Атрибут findValue  
  
|Значение|Описание|  
|-----------|-----------------|  
|String|Значение зависит от поля (заданного атрибутом x509FindType), поиск которого выполняется. Например, при поиске отпечатка значение должно быть строкой шестнадцатеричных чисел.|  
  
## <a name="x509findtype-attribute"></a>Атрибут x509FindType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. (FindByThumbprint, FindBySubjectName, Финдбисубжектдистингуишеднаме, Финдбиссуернаме, Финдбиссуердистингуишеднаме, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , Финдбяппликатионполици, Финдбицертификатеполици, Финдбекстенсион, Финдбикэйусаже, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Атрибут storeLocation  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|CurrentUser или LocalMachine.|  
  
## <a name="storename-attribute"></a>Атрибут storeName  
  
|Значение|Описание|  
|-----------|-----------------|  
|Перечисление|К этим значениям относятся следующие. AddressBook, Аусрут, CertificateAuthority, запрещено, My, root, TrustedPeople и Трустедпублишер.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Кновнцертификатес >](knowncertificates.md)|Представляет коллекцию сертификатов X.509, предоставленную службой STS для проверки маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 В сценарии с выданным маркером имеется три этапа. На первом этапе клиент, пытающийся получить доступ к службе, ссылается на *службу маркеров безопасности*. Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML). После этого клиент возвращается к службе с этим маркером. Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента. Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.  
  
 Элемент [иссуедтокенаусентикатион > — это репозиторий для любых таких сертификатов службы безопасных маркеров. \<](issuedtokenauthentication-of-servicecredentials.md) Чтобы добавить сертификаты, используйте [ \<> кновнцертификатес](knowncertificates.md). Вставьте элемент [ \<Add > кновнцертификатес>длякаждогосертификата,какпоказано\<](add-of-knowncertificates.md) в следующем примере.  
  
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
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется добавление сертификата в хранилище сертификатов службы STS.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<Кновнцертификатес >](knowncertificates.md)
- [Работа с сертификатами](../../../wcf/feature-details/working-with-certificates.md)
- [Федерация и выданные маркеры](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Практическое руководство. Настройка учетных данных на служба федерации](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Защита служб и клиентов](../../../wcf/feature-details/securing-services-and-clients.md)
