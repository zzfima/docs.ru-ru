---
title: "&lt;dataContractSerializer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<dataContractSerializer>, элемент"
  - "DataContractSerializer"
  - "dataContractSerializer, элемент"
  - "KnownTypes"
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &lt;dataContractSerializer&gt;
Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.  Этот элемент присутствует в двух разных иерархиях.  Одна из них указана в следующем разделе «Иерархия схемы», а другая \- в разделе «Примечания».  
  
## Синтаксис  
  
```  
  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Элемент|Описание|  
|-------------|--------------|  
|ignoreExtensionDataObject|Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации.  Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации.  Этот атрибут имеет значение 65 536.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Коллекция параметров для поведения службы.|  
|[\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Заметки  
 Как указано во введение к этому разделу, это вторая иерархия, в которой появляется элемент \<X509Extension\>.  
  
 [\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>   
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [Передача данных и сериализация](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)