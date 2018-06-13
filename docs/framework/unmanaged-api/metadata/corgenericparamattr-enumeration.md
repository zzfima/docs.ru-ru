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
ms.openlocfilehash: 9d56be8c6f224010da22803894524299c0d376ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443542"
---
# <a name="corgenericparamattr-enumeration"></a>Перечисление CorGenericParamAttr
Содержит значения, описывающие <xref:System.Type> параметры универсальных типов, использующихся в вызовах для [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
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
|`gpVarianceMask`|Дисперсия параметра применяется только к универсальным параметрам для интерфейсов и делегатов.|  
|`gpNonVariant`|Указывает на отсутствие дисперсии.|  
|`gpCovariant`|Указывает на ковариацию.|  
|`gpContravariant`|Указывает на контравариантность.|  
|`gpSpecialConstraintMask`|Особые ограничения можно применить к любому <xref:System.Type> параметра.|  
|`gpNoSpecialConstraint`|Указывает, что ограничение не применяется к <xref:System.Type> параметра.|  
|`gpReferenceTypeConstraint`|Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.|  
|`gpNotNullableValueTypeConstraint`|Указывает, что <xref:System.Type> параметр должен быть типом значения, который не может иметь значение null.|  
|`gpDefaultConstructorConstraint`|Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает никаких параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
