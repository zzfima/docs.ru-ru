---
title: "&lt;удостоверение&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;удостоверение&gt;
Элемент identity позволяет разработчику клиента указать во время разработки ожидаемое удостоверение службы.  Во время процесса подтверждения между клиентом и службой инфраструктура [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] обеспечивает соответствие удостоверения ожидаемой службы значению этого элемента. Таким образом происходит проверка подлинности.  Для получения дополнительной информации см. [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Синтаксис  
  
```  
  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|certificate|Задает параметры сертификата X.509.  Это элемент типа <xref:System.ServiceModel.Configuration.CertificateElement>.  Он содержит атрибут `encodedValue`, являющийся строкой, указывающей значение, зашифрованное с помощью этого сертификата.|  
|certificateReference|Задает параметры для проверки сертификата X.509.  Это элемент типа <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Задает службу DNS\-сертификата X.509, используемого для проверки подлинности службы.  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|rsa|Задает значение поля RSA сертификата X.509, используемое для проверки подлинности службы для клиента.  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое удостоверение.|  
|servicePrincipalName|Задает удостоверение имени участника\-сервера, являющегося именем участника, используемым клиентом для уникальной идентификации экземпляра службы.  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.  Это элемент типа <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Задает удостоверение имени участника\-пользователя, являющегося именем входа пользователя в сеть.  Имя участника\-пользователя состоит из имени объекта пользователя, используемого в Active Directory, за которым следует символ \(@\), а затем обычно следует родительский домен службы доменных имен.  Например, у Джефа в дереве домена Fabrikam.com может быть имя участника\-пользователя [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  Этот элемент содержит атрибут `value`, являющийся строкой, и содержит фактическое имя участника.  Это элемент типа <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<пользовательский\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|Задает настраиваемый одноранговый распознаватель для netPeerTcpBinding.|  
|[\<endpoint\>](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017)|Настраивает разные типы конечных точек.|  
|[\<issuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|Задает службу маркеров безопасности для федеративной службы.|  
|[\<issuerMetadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|Задает конечную точку метаданных для службы маркеров безопасности федеративной службы.|  
|[\<issuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Задает параметры для выданного маркера в настраиваемой привязке.|  
|[\<localIssuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|Задает локальную службу маркеров безопасности.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Конечные точки: адреса, привязки и контракты](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)