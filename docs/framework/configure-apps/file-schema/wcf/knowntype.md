---
title: "&lt;knownType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;knownType&gt;
Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.  Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа». Для получения дополнительной информации см. [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## Синтаксис  
  
```  
  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## Тип  
 `string`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|тип|Задает тип \(в том числе пространство имен\), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<параметр\>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|Задает индекс параметра в том случае, если объявленный тип является универсальным типом.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Добавляет объявленный тип в коллекцию объявленных типов.|  
  
## Заметки  
 Дополнительные сведения об известных типах см. в разделах [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Пример использования этого элемента см. в разделе [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
## Пример  
  
```  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)