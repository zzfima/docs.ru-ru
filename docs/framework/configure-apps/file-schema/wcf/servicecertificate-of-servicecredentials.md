---
title: "&lt;serviceCertificate&gt; для &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;serviceCertificate&gt; для &lt;serviceCredentials&gt;
Задает сертификат X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений.  
  
## Синтаксис  
  
```  
  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509.  Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType.  Значение по умолчанию \- пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера.  Допустимы следующие значения:<br /><br /> -   LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-   CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию \- LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509.  Допустимы следующие значения:<br /><br /> -   AddressBook: хранилище сертификатов для других пользователей.<br />-   AuthRoot: хранилище сертификатов для сторонних центров сертификации.<br />-   CertificatAuthority: хранилище сертификатов для промежуточных центров сертификации \(ЦС\).<br />-   Disallowed: хранилище сертификатов для отозванных сертификатов.<br />-   My: хранилище сертификатов для личных сертификатов.<br />-   Root: хранилище сертификатов для доверенных корневых центров сертификации.<br />-   TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-   TrustedPublisher: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию \- My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509.  Допустимы следующие значения:<br /><br /> -   FindByThumbprint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Значение по умолчанию \- FindBySubjectDistinguishedName.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## Заметки  
 Этот элемент используется для задания сертификата X.509, который будет использоваться для проверки подлинности службы при подключении к клиентам с использованием режима безопасности сообщений.  Если используется сертификат, который будет периодически обновляться, то его отпечаток изменится.  В этом случае следует использовать имя субъекта в виде `X509FindType`, поскольку сертификат может быть выдан повторно с тем же именем субъекта.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] использовании элемента см. в разделе [Практическое руководство. Задание значений учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>   
 [Практическое руководство. Задание значений учетных данных клиента](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)