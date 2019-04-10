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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220504"
---
# <a name="corgenericparamattr-enumeration"></a>Перечисление CorGenericParamAttr
Содержит значения, описывающие <xref:System.Type> параметров для универсальных типов, использующихся в вызовах [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`gpVarianceMask`|Параметр Вариативность применяется только к универсальным параметрам для интерфейсов и делегатов.|  
|`gpNonVariant`|Указывает на отсутствие дисперсии.|  
|`gpCovariant`|Указывает ковариации.|  
|`gpContravariant`|Указывает на контравариантность.|  
|`gpSpecialConstraintMask`|Особые ограничения могут применяться к любому <xref:System.Type> параметра.|  
|`gpNoSpecialConstraint`|Указывает, что ограничение не применяется к <xref:System.Type> параметра.|  
|`gpReferenceTypeConstraint`|Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.|  
|`gpNotNullableValueTypeConstraint`|Указывает, что <xref:System.Type> параметр должен иметь тип значения, который не может иметь значение null.|  
|`gpDefaultConstructorConstraint`|Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает никаких параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
