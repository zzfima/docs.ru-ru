---
title: "&lt;security&gt; для &lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;security&gt; для &lt;peerTransport&gt;
Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.  
  
## Синтаксис  
  
```  
  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`mode`|Задает тип применяемого механизма обеспечения безопасности.  Значение по умолчанию \- Message.  Это атрибут типа <xref:System.ServiceModel.SecurityMode>.|  
  
## Атрибут mode  
  
|Значение|Описание|  
|--------------|--------------|  
|`None`|Режим безопасности отключен.|  
|`Transport`|Безопасность обеспечивается с помощью протокола HTTPS.|  
|`Message`|Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.|  
|`TransportWithMessageCredential`|HTTPS обеспечивает конфиденциальность и проверку подлинности.  Сообщения SOAP предоставляют различные типы учетных данных.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки.  Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.  Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<peerTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Определяет одноранговый транспорт для пользовательской привязки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)