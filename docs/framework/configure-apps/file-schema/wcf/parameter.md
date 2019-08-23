---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: c3f2179835ad1232e115cad0decdd3d41bbdc160
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932836"
---
# <a name="parameter"></a>\<> параметра
Указывает общий параметр, если объявленный тип является общим типом.  
  
 \<System. Runtime. Serialization >  
\<dataContractSerializer >  
\<Элемент > declaredTypes  
\<Добавление элемента > для \<declaredTypes >  
\<Элемент > knownType  
\<Элемент > параметра  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|индекс|Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.|  
|type|Строка, которая описывает известный тип, используемый для сериализации и десериализации.|  
  
## <a name="index-attribute"></a>Атрибут index  
  
|Значение|Описание|  
|-----------|-----------------|  
|"0"|Первый параметр в общем типе. Например, у <xref:System.Collections.Generic.List%601> есть только один параметр. Если он используется как объявленный тип, индексу присваивается значение 0.|  
|"1"|Второй параметр в общем типе. Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра. Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<knownType >](knowntype.md)|Указывает известный тип, который может возвращаться полем или свойством объявленного типа.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Пример использования этого элемента см. в [ \<> dataContractSerializer](datacontractserializer-element.md) .  
  
 У данного элемента конфигурации не может одновременно быть оба атрибута. Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Известные типы контрактов данных](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer >](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
