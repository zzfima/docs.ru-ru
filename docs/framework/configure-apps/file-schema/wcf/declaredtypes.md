---
title: '&lt;declaredTypes&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1cd7d446b0d86e1f38e38afeee03161278afed7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="ltdeclaredtypesgt"></a>&lt;declaredTypes&gt;
Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.  
  
 Дополнительные сведения о контрактах данных и известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 system.runtime.serialization  
\<dataContractSerializer >  
\<declaredTypes >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Добавляет типы, для которых необходимы известные типы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="example"></a>Пример  
 Приведенный ниже код XML показывает объявленные типы и известные типы, добавленные к `DataContractSerializer` элемента. В этом примере показаны три добавляемых типа. Первый тип - это пользовательский тип с именем «Orders», использующий известный тип с именем «Item». Второй объявленный тип - это <xref:System.Collections.Generic.List%601>, использующий `Item` в качестве известного типа. Наконец, третий объявленный тип - это <xref:System.Collections.Generic.Dictionary%602>. Тип класса <xref:System.Collections.Generic.Dictionary%602> является универсальным типом с двумя параметрами типов. Первый представляет ключ, а второй представляет значение. В следующем примере параметр второго типа <xref:System.Collections.Generic.List%601> (значение) добавляется к списку известных типов. Чтобы задать параметр типа для использования в известном типе, необходимо использовать атрибут `index`. В данном примере тип значения указан атрибутом индекса, для которого задано значение 1 (коллекция начинается с нуля).  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
