---
title: "&lt;servicePrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;servicePrincipalName&gt;
Указывает идентификацию службы по имени участника\-службы \(SPN\).  
  
 Дополнительные сведения о настройке SPN см. в разделе [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Синтаксис  
  
```  
  
<servicePrincipalName value = "String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|value|Имя, по которому клиент однозначно идентифицирует экземпляр службы.  Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника\-службы.  Каждый экземпляр службы может иметь несколько имен участников\-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## Заметки  
 Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует SPN при выполнении проверки подлинности SSPI в конечной точке.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.SpnEndpointIdentity>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)