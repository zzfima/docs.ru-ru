---
title: "&lt;userPrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;userPrincipalName&gt;
Задает имя участника\-пользователя \(UPN\) для службы, подлинность которой должна быть проверена клиентом.  
  
 Дополнительные сведения о параметрах UPN см. в разделе [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Синтаксис  
  
```  
  
<userPrincipalName value = "String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|value|Имя учетной записи пользователя \(которая иногда называется именем входа пользователя\) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.  Это стандартный способ входа в домен Windows.  Используется следующий формат: someone@example.com \(аналогично адресу электронной почты\).|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## Заметки  
 Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует UPN при выполнении проверки подлинности SSPI в конечной точке.  
  
## Пример  
 Приводимый ниже код конфигурации задает имя участника\-пользователя \(UPN\) для службы, подлинность которой должна быть проверена клиентом.  
  
```  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.UpnEndpointIdentity>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)