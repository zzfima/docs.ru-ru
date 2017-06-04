---
title: "&lt;clientCertificate&gt; для &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;clientCertificate&gt; для &lt;serviceCredentials&gt;
Задает файл сертификата X.509, используемый для подписания и шифрования сообщений к клиенту от службы при дуплексном обмене данными.  
  
## Синтаксис  
  
```  
  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<authentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|Задает параметры проверки подлинности для сертификата клиента.|  
|[\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|Задает тип сертификата для использования.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## Заметки  
 Этот элемент используется в случаях, когда служба должна получить клиентский сертификат заранее для безопасного обмена данными с клиентом.  Это характерно для дуплексного обмена данными.  В более распространенном варианте «запрос\/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика.  Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту.  Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента.  Дополнительные сведения о дуплексных службах см. в разделе [Как создавать дуплексный контракт](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 Заданный в этом элементе сертификат используется для шифрования сообщений к клиенту только для привязок, которые настроены с использованием режима проверки подлинности `MutualCertificateDuplex`.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>   
 [Как создавать дуплексный контракт](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)