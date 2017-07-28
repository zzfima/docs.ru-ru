---
title: "&lt;add&gt; для &lt;authorizationPolicies&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; для &lt;authorizationPolicies&gt;
Задает политику авторизации для преобразования требований.  
  
## Синтаксис  
  
```  
  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`policyType`|Обязательный строковый атрибут.<br /><br /> Модель управления доступом [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] поддерживает предоставление набора политик авторизации в качестве типов.  Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.  В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<authorizationPolicies\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|Задает коллекцию типов политики авторизации.|  
  
## Заметки  
 Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.  Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.  В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.  Дополнительные сведения о работе политики авторизации см. в разделах <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [Политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>   
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>   
 [Авторизация доступа к операциям службы](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Как создавать пользовательский диспетчер авторизации для службы](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)   
 [Политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md)