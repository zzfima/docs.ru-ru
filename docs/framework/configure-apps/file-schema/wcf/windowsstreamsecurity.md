---
title: "&lt;windowsStreamSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;windowsStreamSecurity&gt;
Задает параметры безопасности потока Windows пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|protectionLevel|Определяет систему безопасности уровня сообщений.  Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.  Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.  Допустимы следующие значения:<br /><br /> -   None: не защищено.<br />-   Sign: сообщения подписываются.<br />-   EncryptAndSign: сообщения подписываются и шифруются.<br /><br /> Значение по умолчанию \- EncryptAndSign.<br /><br /> Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Транспорты, использующие такой поточно\-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.  В частности, WCF обеспечивает обновления системы безопасности.  Конфигурация этой системы безопасности транспорта инкапсулируется элементом конфигурации так же, как и [\<sslStreamSecurity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), который может быть настроен и добавлен в пользовательской привязку.  
  
## См. также  
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>   
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)