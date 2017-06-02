---
title: "&lt;add&gt; для &lt;allowAccounts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;add&gt; для &lt;allowAccounts&gt;
Определяет учетную запись пользователя для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.  
  
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
  
|Атрибут|Описание|  
|-------------|--------------|  
|securityIdentifier|Строка, задающая уникальный идентификатор, который используется для идентификации учетной записи пользователя.  Значениями по умолчанию являются LocalSystem, Administrators, NS, LS и IIS\_USRS.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<allowAccounts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.|  
  
## Пример  
 В следующем примере конфигурации к данной коллекции добавляется пять идентификаторов по умолчанию для учетных записей пользователей.  
  
```  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>