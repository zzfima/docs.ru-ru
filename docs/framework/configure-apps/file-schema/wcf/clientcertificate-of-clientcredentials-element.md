---
title: "&lt;clientCertificate&gt; элемента &lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;clientCertificate&gt; элемента &lt;clientCredentials&gt;
Определяет сертификат X.509, используемый для проверки подлинности клиента при подключении к службе.  
  
## Синтаксис  
  
```  
  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509.  Тип, указанный в атрибуте, должен отвечать требованиям к значению атрибута `X509FindType`.  Значение по умолчанию \- пустая строка.|  
|`storeLocation`|Указывает расположение сертификата X.509, который клиент использует для подтверждения подлинности при взаимодействии со службой.  Допустимы следующие значения:<br /><br /> -   LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-   CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию \- LocalMachine.  Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Задает имя хранилища сертификатов X.509 для поиска.  Допустимы следующие значения:<br /><br /> -   AddressBook: хранилище сертификатов для других пользователей.<br />-   AuthRoot: хранилище сертификатов для сторонних центров сертификации \(ЦС\).<br />-   CertificateAuthority: хранилище сертификатов для промежуточных центров сертификации \(ЦС\).<br />-   Disallowed: хранилище сертификатов для отозванных сертификатов.<br />-   My: хранилище сертификатов для личных сертификатов.<br />-   Root: хранилище сертификатов для доверенных корневых центров сертификации \(ЦС\).<br />-   TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-   TrustedPublisher: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию \- My.  Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Определяет тип поиска сертификата X.509.  Тип, указанный в атрибуте `findValue`, должен отвечать требованиям этого атрибута.  Допустимы следующие значения:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Значение по умолчанию \- FindBySubjectDistinguishedName.  Это атрибут типа <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## Заметки  
 Этот элемент конфигурации указывает сертификат, используемый для проверки подлинности клиента с помощью этого элемента.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Практическое руководство. Задание значений учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Практическое руководство. Задание значений учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)