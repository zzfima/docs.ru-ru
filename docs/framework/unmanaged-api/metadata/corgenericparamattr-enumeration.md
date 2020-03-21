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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176179"
---
# <a name="corgenericparamattr-enumeration"></a>Перечисление CorGenericParamAttr
Содержит значения, описывающие <xref:System.Type> параметры для генерических типов, используемые при вызовах на [IMetaDataEmit2::DefineGenericParam.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)  
  
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
  
|Участник|Описание|  
|------------|-----------------|  
|`gpVarianceMask`|Разница параметров применяется только к общим параметрам для интерфейсов и делегатов.|  
|`gpNonVariant`|Указывает на отсутствие дисперсии.|  
|`gpCovariant`|Указывает на коварность.|  
|`gpContravariant`|Указывает на противопоказания.|  
|`gpSpecialConstraintMask`|Специальные ограничения могут <xref:System.Type> применяться к любому параметру.|  
|`gpNoSpecialConstraint`|Означает, что к параметру <xref:System.Type> не применяется ограничение.|  
|`gpReferenceTypeConstraint`|Означает, <xref:System.Type> что параметр должен быть эталонным типом.|  
|`gpNotNullableValueTypeConstraint`|Означает, <xref:System.Type> что параметр должен быть типом значения, который не может быть нулевая величина.|  
|`gpDefaultConstructorConstraint`|Означает, <xref:System.Type> что параметр должен иметь общедоступный конструктор по умолчанию, который не принимает никаких параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
