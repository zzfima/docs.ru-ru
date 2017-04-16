---
title: "&lt;transport&gt; для &lt;netPeerTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;transport&gt; для &lt;netPeerTcpBinding&gt;
Задает параметры безопасности уровня транспорта при использовании [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).  
  
## Синтаксис  
  
```  
  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|credentialType|Необязательно.  Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.  Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## Атрибут credentialType  
  
|Значение|Описание|  
|--------------|--------------|  
|Сертификат|Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.|  
|Пароль|Для проверки подлинности однорангового транспорта канала необходим правильный пароль.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|Определяет параметры безопасности для [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)