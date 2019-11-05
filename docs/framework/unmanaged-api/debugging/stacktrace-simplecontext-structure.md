---
title: Структура StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139134"
---
# <a name="stacktrace_simplecontext-structure"></a>Структура StackTrace_SimpleContext
Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`StackOffset`|Указатель стека или ввод указателя стека (ESP) на платформах x86.|  
|`FrameOffset`|Смещение кадра или регистр EBP на платформах x86.|  
|`InstructionOffset`|Указатель инструкции или ввод указателя инструкции (EIP) на платформах x86.|  
  
## <a name="remarks"></a>Заметки  
 Так как функции трассировки стека обычно должны возвращать только адрес, Смещение фрейма и адрес стека, при необходимости можно использовать структуру `SimpleContext` вместо большой структуры `CONTEXT`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
