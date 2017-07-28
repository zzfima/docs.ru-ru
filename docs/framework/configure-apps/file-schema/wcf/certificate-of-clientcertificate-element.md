---
title: "&lt;certificate&gt; элемента &lt;clientCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;certificate&gt; элемента &lt;clientCertificate&gt;
Указывает сертификат X.509, используемый для подписания и шифрования сообщений.  
  
## Синтаксис  
  
```  
  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509.  Тип, указанный в атрибуте, должен отвечать требованиям заданного значения X509FindType.  Значение по умолчанию \- пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент использует для проверки сертификата сервера.  Допустимы следующие значения:<br /><br /> -   LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-   CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию \- LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509.  Допустимы следующие значения:<br /><br /> -   AddressBook: хранилище сертификатов для других пользователей.<br />-   AuthRoot: хранилище сертификатов для сторонних центров сертификации.<br />-   CertificationAuthority: хранилище сертификатов для промежуточных центров сертификации \(ЦС\).<br />-   Disallowed: хранилище сертификатов для отозванных сертификатов.<br />-   My: хранилище сертификатов для личных сертификатов.<br />-   Root: хранилище сертификатов для доверенных корневых центров сертификации.<br />-   TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-   TrustedPublisher: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию \- My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509.  Допустимы следующие значения:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения X509FindType.<br /><br /> Значение по умолчанию \- FindBySubjectDistinguishedName.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## Заметки  
 Элемент `<certificate>` используется в случаях, когда служба должна заранее получить клиентский сертификат для безопасного обмена данными с клиентом.  Это характерно для дуплексного обмена данными.  В более распространенном варианте «запрос\/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.  Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.  Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.  Дополнительные сведения о дуплексных службах см. в разделе [Как создавать дуплексный контракт](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## Пример  
 В следующем примере кода демонстрируется поиск соответствующего сертификата X.509 и пользовательского типа проверки в элементе `<authentication>`.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)