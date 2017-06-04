---
title: "&lt; add&gt; элемента &lt;declaredTypes&gt; | Microsoft Docs"
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
  - "контракты данных"
  - "DataContractAttribute"
  - "DataContractSerializer"
  - "dataContractSerializer, элемент"
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt; add&gt; элемента &lt;declaredTypes&gt;
Добавляет тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации.  В каждый объявленный тип включены известные типы, которые будут возвращены как поле или свойство объявленного типа.  
  
## Синтаксис  
  
```  
  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|тип|Обязательный строковый атрибут.<br /><br /> Задает имя типа \(в том числе пространство имен\), имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Задает известный тип для добавляемого объявленного типа.  Если объявленный тип является универсальным типом, необходимо также добавить элемент параметра к элементу `<knownType>`, чтобы указать, какой универсальный параметр будет использоваться для возвращения известного типа.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<declaredTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Содержит типы, для которых необходимы известные типы во время десериализации с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Заметки  
 Дополнительные сведения об известных типах см. в разделах [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Пример использования этого элемента см. в разделе [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
> [!NOTE]
>  При добавлении типа <xref:System.Object> как `<declaredType>` возникает <xref:System.Configuration.ConfigurationErrorsException>.  Это обусловлено тем, что тип <xref:System.Object> нельзя использовать как объявленный тип в конфигурации.  
  
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
 [\<add\> of \<declaredTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)