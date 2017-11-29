---
title: "Структура StackTrace_SimpleContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackTrace_SimpleContext
api_location: diasymreader.dll
api_type: COM
f1_keywords: SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87ce3d50d6da6a7c23b13fa10123033efbb6c52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="stacktracesimplecontext-structure"></a>Структура StackTrace_SimpleContext
Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`StackOffset`|Указатель стека или вводный указатель стека (ESP) на x86 платформы.|  
|`FrameOffset`|Смещение фрейма или регистр EBP на x86 платформы.|  
|`InstructionOffset`|Указатель инструкций или вводный указатель инструкций (EIP) на x86 платформы.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку обычно требуется вернуть только адрес, смещение кадра и стека адрес функции трассировки стека, при необходимости можно использовать `SimpleContext` структуры вместо большой `CONTEXT` структуры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
