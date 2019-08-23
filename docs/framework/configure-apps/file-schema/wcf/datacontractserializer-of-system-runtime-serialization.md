---
title: <dataContractSerializer>< System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 380d9ba5b8407d78b5045fd34fcdf37c0818d6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919350"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a>\<dataContractSerializer > \<System. Runtime. Serialization >
Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<System. Runtime. Serialization >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Логическое значение, указывающее, пропускать ли данные, предоставленные конечной точкой при ее сериализации или десериализации. Этот атрибут можно задать только в `<dataContractSerializer>` в элементе `<behavior>`.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации. Этот атрибут имеет значение 65 536.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<declaredTypes >](declaredtypes.md)|Содержит известные типы, которые <xref:System.Runtime.Serialization.DataContractSerializer> использует при десериализации.<br /><br /> Дополнительные сведения о контрактах данных и известных типах см. в статье о [известных типах контрактов данных](../../../wcf/feature-details/data-contract-known-types.md).|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в <xref:System.Runtime.Serialization.DataContractSerializer> разделе и [известные типы контракта данных](../../../wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [Известные типы контрактов данных](../../../wcf/feature-details/data-contract-known-types.md)
