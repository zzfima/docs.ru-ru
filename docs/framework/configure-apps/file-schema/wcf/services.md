---
title: "&lt;службы&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;службы&gt;
Службы задаются в разделе `services` файла конфигурации.  Для каждой службы используется собственный раздел конфигурации `service`.  
  
 \<system.ServiceModel\>  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<service\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Определяет контракт службы, поведение и конечные точки конкретной службы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation \(WCF\).|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServicesSection>