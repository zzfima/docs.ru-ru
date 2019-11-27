---
title: Перечисление CorGenericParamAttr
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: e4abf876681d5b04555c9f030a94b722874e326e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450281"
---
# <a name="corgenericparamattr-enumeration"></a>Перечисление CorGenericParamAttr
Содержит значения, описывающие параметры <xref:System.Type> для универсальных типов, которые используются в вызовах метода [IMetaDataEmit2::D ефинеженерикпарам](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`gpVarianceMask`|Дисперсия параметров применяется только к универсальным параметрам для интерфейсов и делегатов.|  
|`gpNonVariant`|Указывает отсутствие дисперсии.|  
|`gpCovariant`|Указывает ковариацию.|  
|`gpContravariant`|Указывает контрвариация.|  
|`gpSpecialConstraintMask`|Специальные ограничения могут применяться к любому параметру <xref:System.Type>.|  
|`gpNoSpecialConstraint`|Указывает, что ограничение не применяется к параметру <xref:System.Type>.|  
|`gpReferenceTypeConstraint`|Указывает, что параметр <xref:System.Type> должен быть ссылочным типом.|  
|`gpNotNullableValueTypeConstraint`|Указывает, что параметр <xref:System.Type> должен быть типом значения, который не может иметь значение null.|  
|`gpDefaultConstructorConstraint`|Указывает, что параметр <xref:System.Type> должен иметь открытый конструктор по умолчанию, который не принимает параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
