---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783439"
---
# <a name="parameter"></a>\<Параметр >
Указывает общий параметр, если объявленный тип является общим типом.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer >  
\<declaredTypes > элемент  
\<Добавить > элемент для \<declaredTypes >  
\<knownType > элемент  
\<параметр > элемент  
  
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
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Указывает известный тип, который может возвращаться полем или свойством объявленного типа.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 См. в разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.  
  
 У данного элемента конфигурации не может одновременно быть оба атрибута. Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
