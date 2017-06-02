---
title: "Раздел &lt;extensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Раздел &lt;extensions&gt;
Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.  
  
 \<system.ServiceModel\>  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <extensions>  
      <bindingExtensions>  
      </bindingExtensions>  
      <behaviorExtensions>  
      </behaviorExtensions>  
      <bindingElementExtensions>  
      </bindingElementExtensions>  
      <endpointExtensions>  
      </endpointExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<behaviorExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.|  
|[\<bindingElementExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.|  
|[\<bindingExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.|  
|[\<endpointExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|system.ServiceModel|Корневой элемент всех элементов конфигурации WCF.|