---
title: "&lt;dns&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;dns&gt;
Задает ожидаемое удостоверение сервера.  Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.  Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.  
  
 Дополнительные сведения об установке значения элемента см. в разделе [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Синтаксис  
  
```  
  
<dns value = "String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|value|Сервер DNS сертификата.  Протокол DNS \- это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.  Пользователям проще запоминать отображаемые имена, например [http:\/\/go.microsoft.com\/fwlink\/?prd\=10929](http://go.microsoft.com/fwlink/?prd=10929) или [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=96165](http://go.microsoft.com/fwlink/?LinkID=96165), чем числовые адреса, например 207.46.131.137.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## Пример  
 В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.  
  
```  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.DnsEndpointIdentity>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)