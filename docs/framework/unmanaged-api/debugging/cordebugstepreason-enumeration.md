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
ms.openlocfilehash: 92aee981aca3bac32c0ef264799e486315ca5103
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789254"
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
  
## <a name="members"></a>Участники  
  
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
  
## <a name="see-also"></a>См. также:

- [Метод StepComplete](icordebugmanagedcallback-stepcomplete-method.md)
- [Перечисления отладки](debugging-enumerations.md)
