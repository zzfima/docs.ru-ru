---
title: "Элемент &lt;scopedCertificates&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Элемент &lt;scopedCertificates&gt;
Представляет коллекцию сертификатов X.509, предоставленную конкретными службами \(в области действия\) для проверки подлинности.  Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.  
  
## Синтаксис  
  
```  
  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|Добавляет сертификат X.509 в коллекцию сертификатов в области действия.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|Задает сертификат для использования при проверке подлинности службы для клиента.|  
  
## Заметки  
 Эта коллекция позволяет клиенту настроить сертификаты служб для использования на основе URL\-адреса службы, с которой он связывается.  Это особенно полезно в сценариях с выданным маркером, в которых клиент может связываться с несколькими службами \(с конечной службой, а также с промежуточными службами маркеров безопасности\).  Для привязок, в которых используется безопасность сообщений на основе сертификатов, этот сертификат используется для шифрования сообщений службе; предполагается также, что он будет использоваться службой для подписи ответов клиенту.  
  
 Если для привязки необходим сертификат для службы, а конкретный сертификат для URL\-адреса службы в элементе ScopedCertificates отсутствует, то используется сертификат по умолчанию.  
  
 Дополнительные сведения см. в разделе «Сертификаты в области действия» [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## Пример  
 В следующем примере задается сертификат службы для клиента для использования при связи по протоколу HTTP с конечными точками, именем домена которых является http:\/\/www.contoso.com.  
  
```  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)