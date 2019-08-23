---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928865"
---
# <a name="knowntype"></a>\<knownType >
Задает тип, используемый <xref:System.Runtime.Serialization.DataContractSerializer> во время десериализации. Элемент задает «известный тип», возвращаемый полем или свойством «объявленного типа». Дополнительные сведения см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).  
  
 \<System. Runtime. Serialization >  
\<dataContractSerializer >  
\<Элемент > declaredTypes  
\<Добавление > \<> declaredTypes  
\<Элемент > knownType  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a>Тип  
 `string`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Задает тип (в том числе пространство имен), имя сборки, версию, язык и региональные параметры и маркер открытого ключа.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> параметра](parameter.md)|Задает индекс параметра в том случае, если объявленный тип является универсальным типом.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|Добавляет объявленный тип в коллекцию объявленных типов.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Известные типы контрактов данных](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer >](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
