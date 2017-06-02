---
title: "&lt;declaredTypes&gt; | Microsoft Docs"
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
  - "элемент <declaredTypes>"
  - "DataContractSerializer"
  - "dataContractSerializer, элемент"
  - "declaredTypes, элемент"
  - "KnownTypes"
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;declaredTypes&gt;
Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.  
  
 Дополнительные сведения о контрактах данных и известных типах см. в разделе [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## Синтаксис  
  
```  
  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
                <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Добавляет типы, для которых необходимы известные типы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Заметки  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] известных типах\[см. в разделах [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Пример  
 Следующий код XML показывает объявленные типы и известные типы, добавленные к элементу `DataContractSerializer` .  В этом примере показаны три добавляемых типа.  Первый тип \- это пользовательский тип с именем «Orders», использующий известный тип с именем «Item».  Второй объявленный тип \- это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа.  Наконец, третий объявленный тип \- это <xref:System.Collections.Generic.Dictionary%602>.  Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов.  Первый представляет ключ, а второй представляет значение.  В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> \(значение\) добавляется к списку известных типов.  Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`.  В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 \(коллекция начинается с нуля\).  
  
```  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
            <parameter index="1"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)