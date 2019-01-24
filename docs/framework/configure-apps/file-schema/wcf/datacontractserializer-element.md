---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: d8e0f2ac6e417609ec17d345d1cb20f2a4255dba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657597"
---
# <a name="ltdatacontractserializergt"></a>&lt;DataContractSerializer&gt;
Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>. Этот элемент присутствует в двух разных иерархиях. Одна из них указана в следующем разделе «Иерархия схемы», а другая - в разделе «Примечания».  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации. Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации. Этот атрибут имеет значение 65 536.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Коллекция параметров для поведения службы.|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Примечания  
 Как уже говорилось в начале этого раздела, это вторая иерархия, в которой \<X509Extension > происходит элемент.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Дополнительные сведения об известных типах см. в разделе <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Передача данных и сериализация](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
