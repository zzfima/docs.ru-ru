---
title: "&lt;certificateReference&gt; для &lt;идентификатора&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;certificateReference&gt; для &lt;идентификатора&gt;
Задает параметры для проверки сертификата X.509.  Защищенный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с использованием этого удостоверения, проверяет, что утверждения, представленные сервером, содержат идентификационное утверждение, используемое для конструирования этого удостоверения.  
  
## Синтаксис  
  
```  
  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|findValue|Задает значение для поиска в хранилище сертификатов X.509.  Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `X509FindType`.  Значение по умолчанию \- пустая строка.|  
|isChainIncluded|Логическое значение, определяющее, выполнена ли проверка с использованием цепочки сертификатов.|  
|storeLocation|Задает расположение хранилища сертификатов, которое клиент может использовать для проверки сертификата сервера.<br /><br /> Допустимы следующие значения:<br /><br /> -   LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-   CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию \- LocalMachine.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Задает имя открываемого хранилища сертификатов X.509.<br /><br /> Допустимы следующие значения:<br /><br /> -   AddressBook: хранилище сертификатов для других пользователей.<br />-   AuthRoot: хранилище сертификатов для сторонних центров сертификации.<br />-   CertificateAuthority: хранилище сертификатов для промежуточных центров сертификации \(ЦС\).<br />-   Disallowed: хранилище сертификатов для отозванных сертификатов.<br />-   My: хранилище сертификатов для личных сертификатов.<br />-   Root: хранилище сертификатов для доверенных корневых центров сертификации.<br />-   TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-   TrustedPublisher: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию \- «My».<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип выполняемого поиска X.509.  Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Допустимы следующие значения:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Значение по умолчанию \- FindBySubjectDistinguishedName.<br /><br /> Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает параметры, которые обеспечивают проверку подлинности конечной точки другими конечными точками, с которыми происходит обмен сообщениями.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>   
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>