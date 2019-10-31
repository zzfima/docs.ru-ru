---
title: Перечисление CorDebugIntercept
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 144bdb1b4e479c1e75f89911ad5002e2650e405d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098114"
---
# <a name="cordebugintercept-enumeration"></a>Перечисление CorDebugIntercept
Указывает типы кода, которые могут быть перехвачены (то есть типы, для которых возможно пошаговое выполнение).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`INTERCEPT_NONE`|Перехват кода невозможен.|  
|`INTERCEPT_CLASS_INIT`|Допускается перехват конструктора.|  
|`INTERCEPT_EXCEPTION_FILTER`|Допускается перехват исключения.|  
|`INTERCEPT_SECURITY`|Допускается перехват кода, который принудительно включает систему безопасности.|  
|`INTERCEPT_CONTEXT_POLICY`|Допускается перехват политики контекста.|  
|`INTERCEPT_INTERCEPTION`|Не используется.|  
|`INTERCEPT_ALL`|Возможен перехват любого кода.|  
  
## <a name="remarks"></a>Заметки  
 Используйте метод [ICorDebugStepper:: сетинтерцептмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) , чтобы установить типы кода, которые могут быть перехвачены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
