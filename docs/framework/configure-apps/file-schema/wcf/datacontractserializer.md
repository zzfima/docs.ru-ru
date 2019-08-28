---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 7952e6cc4d2fe7eaa77e297a650f7ffbd7aec785
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040933"
---
# <a name="datacontractserializer"></a>dataContractSerializer
Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<системой. > ServiceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
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
|ignoreExtensionDataObject|Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
> Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`. В противном случае результирующее поведение является неопределенным.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Известные типы контрактов данных](../../../wcf/feature-details/data-contract-known-types.md)
- [Передача данных и сериализация](../../../wcf/feature-details/data-transfer-and-serialization.md)
