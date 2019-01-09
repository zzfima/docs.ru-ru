---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: a024ca89bd766681f25b992f1d2c66a92e3b31b7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150205"
---
# <a name="datacontractserializer"></a>dataContractSerializer
Содержит данные конфигурации для <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<endpointBehaviors >  
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
|ignoreExtensionDataObject|Логическое значение, указывающее, должны ли пропускаться данные, предоставляемые конечной точкой, при их сериализации или десериализации.|  
|maxItemsInObjectGraph|Целое число, указывающее максимальное количество элементов для сериализации или десериализации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения об известных типах см. в документации по <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
>  Элемент поведения `<dataContractSerializer>` (если он присутствует) должен всегда находиться в файле конфигурации перед элементом поведения `<enableWebScript>`. В противном случае результирующее поведение является неопределенным.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [Известные типы контрактов данных](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Передача данных и сериализация](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
