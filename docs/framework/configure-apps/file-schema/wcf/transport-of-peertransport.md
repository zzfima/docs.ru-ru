---
title: "&lt;transport&gt; для &lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;transport&gt; для &lt;peerTransport&gt;
Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.  
  
## Синтаксис  
  
```  
  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
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
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Определяет параметры безопасности для однорангового транспорта.|  
  
## Заметки  
 Этот элемент задается, только если атрибут режима [\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) имеет значение `Transport` или `TransportWithMessageCredential`.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)