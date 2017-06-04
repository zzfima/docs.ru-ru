---
title: "&lt;issuerMetadata&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;issuerMetadata&gt;
## Синтаксис  
  
```  
  
<issuerMetadata address=String" >  
   <headers>  
      <add name="String"  
                 namespace="String" />  
   </headers>  
   <identity>  
           <certificate encodedValue="String"/>  
      <certificateReference findValue="String"   
         isChainIncluded="Boolean"  
         storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
         storeLocation="LocalMachine/CurrentUser"  
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuerMetadata>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|address|Обязательный атрибут элемента `string`.<br /><br /> Задает адрес конечной точки.  Адрес должен быть абсолютным универсальным кодом ресурса \(URI\).  Значение по умолчанию \- пустая строка.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<верхние колонтитулы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адреса.|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|Определяет параметры безопасности уровня сообщений для элемента [\<wsFederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Возможности безопасности при использовании пользовательских привязок](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)