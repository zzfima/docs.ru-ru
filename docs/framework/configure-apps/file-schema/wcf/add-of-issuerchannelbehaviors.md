---
title: "&lt;add&gt; для &lt;issuerChannelBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; для &lt;issuerChannelBehaviors&gt;
Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.  
  
> [!NOTE]
>  Если поведение какой\-либо конечной точки содержит элемент [\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md), возникает исключение.  
  
## Синтаксис  
  
```  
  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|issuerAddress|Универсальный код ресурса \(URI\) издателя маркера безопасности, с которым осуществляется взаимодействие.|  
|behaviorConfiguration|Имя поведения конечной точки, определенное в том же файле конфигурации.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Содержит коллекцию поведений конечной точки клиента [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые должны использоваться при взаимодействии с заданными службами маркеров безопасности.|  
  
## Заметки  
 `issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.  `behaviorConfiguration` указывает на поведение конечной точки, которое приложение использует в каналах, созданных [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] для получения токенов, выданных локальной службой токенов безопасности.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>   
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Как создавать федеративный клиент](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Как настраивать локальный издатель](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)