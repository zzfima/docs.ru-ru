---
title: "&lt;namedPipeTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;namedPipeTransport&gt;
Задает транспорт, принуждающий канал передавать сообщения с использованием именованных каналов, когда он включается в пользовательскую привязку.  
  
## Синтаксис  
  
```  
  
<namedPipeTransport>  
      <connectionPoolSettings  
         groupName=”String”  
          idleTimeout"TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
</namedPipeTransport>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<connectionPoolSettings\> для \<namedPipeTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Задает дополнительные параметры пула подключений для привязки именованного канала.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Этот транспорт использует универсальные коды ресурсов \(URI\) вида net.pipe:\/\/hostname\/path.  Другие элементы универсального кода ресурса \(URI\) не обязательны.  
  
 Элемент `namedPipeTransport` является отправной точкой для создания пользовательской привязки, реализующей именованные каналы транспорта HTTPS.  Этот транспорт используется для взаимодействия служб WCF на компьютере.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)