---
title: "&lt;defaultPorts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;defaultPorts&gt;
Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.  
  
## Синтаксис  
  
```  
  
<useRequestHeadersForMetadataAddress>  
   <defaultPorts>  
      <add scheme="http" port="integer" />  
   </defaultPorts>  
</useRequestHeadersForMetadataAddress>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<add\> для \<defaultPorts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<useRequestHeadersForMetadataAddress\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Список портов по умолчанию.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>