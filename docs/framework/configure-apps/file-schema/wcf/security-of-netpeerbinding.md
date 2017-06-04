---
title: "&lt;security&gt; для &lt;netPeerBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# &lt;security&gt; для &lt;netPeerBinding&gt;
Определяет параметры безопасности [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), включая используемый тип проверки подлинности и механизм обеспечения безопасности, используемые при транспорте сообщений.  
  
## Синтаксис  
  
```  
  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|Необязательно.  Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.  Значение по умолчанию — `Message`.  Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## Атрибут mode  
  
|Значение|Описание|  
|--------------|--------------|  
|Сообщение|Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.|  
|Нет|Режим безопасности отключен.|  
|Transport|Безопасность обеспечивается с помощью протокола HTTPS.|  
|TransportWithMessageCredential|HTTPS обеспечивает конфиденциальность и проверку подлинности.  Сообщения SOAP предоставляют различные типы учетных данных.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности привязки [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Заметки  
 Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Выбор типа учетных данных](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)