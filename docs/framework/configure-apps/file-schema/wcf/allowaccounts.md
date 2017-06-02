---
title: "&lt;allowAccounts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;allowAccounts&gt;
Содержит коллекцию элементов конфигурации, которые задают учетные записи пользователей для процессов служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые имеют доступ к совместно используемым службам.  
  
 \<system.serviceModel.activation\>  
  
## Синтаксис  
  
```  
  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|Добавляет учетную запись пользователя для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемым службам.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<net.pipe\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) или [\<net.tcp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.|  
  
## См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>