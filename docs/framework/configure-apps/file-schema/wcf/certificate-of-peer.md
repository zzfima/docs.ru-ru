---
title: "&lt;certificate&gt; для &lt;peer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;certificate&gt; для &lt;peer&gt;
Задает сертификат, используемый одноранговым узлом.  
  
## Синтаксис  
  
```  
  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`findValue`|Строка, содержащая значение для поиска в хранилище сертификатов X.509.  Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.  Значение по умолчанию \- пустая строка.|  
|`storeLocation`|Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.  Допустимы следующие значения:<br /><br /> -   LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.<br />-   CurrentUser: хранилище сертификатов, назначенное текущему пользователю.<br /><br /> Значение по умолчанию \- LocalMachine.|  
|`storeName`|Задает имя открываемого хранилища сертификатов X.509.  Допустимы следующие значения:<br /><br /> -   AddressBook: хранилище сертификатов для других пользователей.<br />-   AuthRoot: хранилище сертификатов для сторонних центров сертификации \(ЦС\).<br />-   CertificateAuthority: хранилище сертификатов для промежуточных центров сертификации \(ЦС\).<br />-   Disallowed: хранилище сертификатов для отозванных сертификатов.<br />-   My: хранилище сертификатов для личных сертификатов.<br />-   Root: хранилище сертификатов для доверенных корневых центров сертификации \(ЦС\).<br />-   TrustedPeople: хранилище сертификатов для непосредственно доверенных лиц и ресурсов.<br />-   TrustedPublisher: хранилище сертификатов для непосредственно доверенных издателей.<br /><br /> Значение по умолчанию \- My.|  
|`X509FindType`|Определяет тип поиска сертификата X.509.  Допустимы следующие значения:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.<br /><br /> Значение по умолчанию \- FindBySubjectDistinguishedName.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Задает текущие учетные данные для однорангового узла.|  
  
## Заметки  
 Этот элемент конфигурации содержит экземпляр `X509Certificate2`, используемый при проверке подлинности соседей в сетке узлов.  
  
 Дополнительные сведения об одноранговом программировании см. в разделе [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>   
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>   
 <xref:System.ServiceModel.Security.PeerCredential>   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/ru-ru/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/ru-ru/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)