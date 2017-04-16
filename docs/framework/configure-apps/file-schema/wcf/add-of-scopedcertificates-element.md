---
title: "&lt;add&gt; элемента &lt;scopedCertificates&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; элемента &lt;scopedCertificates&gt;
Добавляет сертификат X.509 в коллекцию сертификатов в области действия.  
  
## Синтаксис  
  
```  
  
<add findValue="String"  
          storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
          targetUri="string"  
         x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"   
/>   
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|targetUri|Строка.  Задает универсальный код ресурса \(URI\) службы, связанной с сертификатом.|  
|findValue|Строка.  Значение, которое нужно найти.|  
|x509FindType|Перечисление.  Одно из полей сертификата, где следует проводить поиск.|  
|storeLocation|Перечисление.  Одно из двух местоположений хранилища, где следует проводить поиск.|  
|storeName|Перечисление.  Одно из системных хранилищ, где следует проводить поиск.|  
  
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
|[\<scopedCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Представляет коллекцию сертификатов X.509, предоставленную конкретными службами \(в области действия\) для проверки подлинности.|  
  
## Заметки  
 Этот элемент позволяет клиенту настроить сертификат службы для использования на основе URL\-адреса службы, с которой он связывается.  Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами \(с конечной службой, а также с промежуточными службами маркеров безопасности\).  Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.  
  
 Если для привязки необходим сертификат для службы, а конкретный сертификат для URL\-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.  
  
 Дополнительные сведения см. в разделе «Сертификаты в области действия» [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## Пример  
 В следующем примере к коллекции добавляется сертификат X.509.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <serviceCertificate>  
     <scopedCertificates>  
      <add targetUri="http://www.contoso.com"   
       findValue="www.Contoso.com"   
       storeLocation="LocalMachine"  
       storeName="Root"   
       x509FindType="FindByIssuerName" />  
     </scopedCertificates>  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>   
 [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)