---
title: "&lt;параметр&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdbb47fcb65273d03d226e13730849170d4345c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltparametergt"></a>&lt;параметр&gt;
Указывает общий параметр, если объявленный тип является общим типом.  
  
 \<System.Runtime.Serialization >  
\<dataContractSerializer >  
\<declaredTypes > элемент  
\<Добавить > элемент для \<declaredTypes >  
\<knownType > элемент  
\<параметр > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|индекс|Если объявленный тип является общим типом, указывает общий параметр, который возвращает известный тип.|  
|тип|Строка, которая описывает известный тип, используемый для сериализации и десериализации.|  
  
## <a name="index-attribute"></a>Атрибут index  
  
|Значение|Описание|  
|-----------|-----------------|  
|"0"|Первый параметр в общем типе. Например, у <xref:System.Collections.Generic.List%601> есть только один параметр. Если он используется как объявленный тип, индексу присваивается значение 0.|  
|"1"|Второй параметр в общем типе. Например, у <xref:System.Collections.Generic.Dictionary%602> есть два параметра. Если известный тип возвращается вторым параметром, атрибуту index присваивается значение 1.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Указывает известный тип, который может возвращаться полем или свойством объявленного типа.|  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]известных типах см. в разделе [известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) и <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 В разделе [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) пример использования этого элемента.  
  
 У данного элемента конфигурации не может одновременно быть оба атрибута. Если заданы оба атрибута, возникает исключение <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
