---
title: "&lt;transportConfigurationTypes&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;transportConfigurationTypes&gt;
Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.  Может использоваться для добавления пользовательских протоколов WAS.  
  
## Синтаксис  
  
```  
  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Имя транспорта|  
|transportConfigurationType|Тип, реализующий транспорт|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|Добавляет элемент конфигурации, который определяет тип конкретного транспорта.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceHostingEnvironment\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Определяет, какой тип среда размещения служб создает для конкретного транспорта.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>   
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>   
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)