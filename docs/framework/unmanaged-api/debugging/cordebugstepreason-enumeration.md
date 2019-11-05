---
title: Перечисление CorDebugStepReason
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 6c73afb00cbd104cff3d310d1369097b459c131e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133676"
---
# <a name="cordebugstepreason-enumeration"></a>Перечисление CorDebugStepReason
Указывает результат отдельного шага.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`STEP_NORMAL`|Пошаговое завершение нормального выполнения в одной и той же функции.|  
|`STEP_RETURN`|Пошаговое продолжение обычно после возвращения функции.|  
|`STEP_CALL`|Пошаговое продолжение обычно в начале вновь вызванной функции.|  
|`STEP_EXCEPTION_FILTER`|Было создано исключение, и управление было передано в фильтр исключений.|  
|`STEP_EXCEPTION_HANDLER`|Было создано исключение, а Управление было передано обработчику исключений.|  
|`STEP_INTERCEPT`|Элемент управления передан перехватчику.|  
|`STEP_EXIT`|Поток завершил работу до завершения шага.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
