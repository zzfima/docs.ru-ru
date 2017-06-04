---
title: "&lt;peer&gt; элемент для элемента &lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;peer&gt; элемент для элемента &lt;clientCredentials&gt;
Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.  
  
## Синтаксис  
  
```  
  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.  .|  
|[\<peerAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Задает параметры проверки подлинности для одноранговых клиентов.|  
|[\<messageSenderAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Задает параметры проверки подлинности для отправителей сообщений.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## Заметки  
 Этот элемент конфигурации задает учетные данные, используемые одноранговым узлом для подтверждения своей подлинности для других узлов в сетке, а также параметры, используемые одноранговым узлом для проверки подлинности других одноранговых узлов.  Дополнительные сведения см. в разделах [Peer Channel Message Authentication](http://msdn.microsoft.com/ru-ru/80e73386-514e-4c30-9e4a-b9ca8c173a95) и [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>   
 <xref:System.ServiceModel.Security.PeerCredential>   
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/ru-ru/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/ru-ru/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)