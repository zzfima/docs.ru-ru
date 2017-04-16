---
title: "&lt;clear&gt; элемента &lt;claimTypeRequirements&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;clear&gt; элемента &lt;claimTypeRequirements&gt;
Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены.  Это обеспечивает запуск пустой коллекции.  
  
## Синтаксис  
  
```  
  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<claimTypeRequirements\>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Задает коллекцию обязательных типов утверждений.  Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> В федеративном сценарии службы предъявляют требования к входящим учетным данным.  Например, входящие учетные данные должны обладать определенным набором типов утверждений.  Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.|  
  
## См. также  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>