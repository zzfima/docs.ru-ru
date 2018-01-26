---
title: "Перечисление CorUnmanagedCallingConvention"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446a948c8809d9f098ede8fbb9b426f6169ce812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a>Перечисление CorUnmanagedCallingConvention
Задает соглашение о вызовах для неуправляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|C языка соглашение о вызовах.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Стандартное соглашение о вызовах.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|«This» соглашение о вызовах.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|«Быстрый» соглашение о вызовах.|  
|`IMAGE_CEE_CS_CALLCONV_C`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Не используется.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR не поддерживает «быстрый» соглашение о вызовах в .NET Framework версии 1.0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
