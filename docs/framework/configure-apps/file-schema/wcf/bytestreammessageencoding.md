---
title: "&lt;byteStreamMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;byteStreamMessageEncoding&gt;
Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.  
  
## Синтаксис  
  
```  
  
<byteStreamMessageEncoding/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|messageVersion|Задает версию SOAP сообщений, отправленных с помощью привязки.  Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.<br /><br /> Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.  Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>   
 [Message Encoding](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Выбор кодировщика сообщений](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)