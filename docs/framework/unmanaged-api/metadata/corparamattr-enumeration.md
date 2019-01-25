---
title: Перечисление CorParamAttr
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d07c6de47038d5c52d76ad8ca8e0a5684551d59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491471"
---
# <a name="corparamattr-enumeration"></a>Перечисление CorParamAttr
Содержит значения, описывающие метаданные параметра метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`pdIn`|Указывает, что этот параметр передается в вызов метода.|  
|`pdOut`|Указывает, что этот параметр передается методом возвращаемого значения.|  
|`pdOptional`|Указывает, что параметр является необязательным.|  
|`pdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`pdHasDefault`|Указывает, что параметр имеет значение по умолчанию.|  
|`pdHasFieldMarshal`|Указывает, что параметр содержит сведения о маршалинге.|  
|`pdUnused`|Не используется.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
