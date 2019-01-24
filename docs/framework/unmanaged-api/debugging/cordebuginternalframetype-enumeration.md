---
title: Перечисление CorDebugInternalFrameType
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cf4c0eb3f9bb36cb45aa93c576b4efddaa93482
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736537"
---
# <a name="cordebuginternalframetype-enumeration"></a>Перечисление CorDebugInternalFrameType
Указывает тип кадра стека. Это перечисление используется с [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Значение Null. `ICorDebugInternalFrame::GetFrameType` Метод никогда не возвращает это значение.|  
|`STUBFRAME_M2U`|Кадр управляемого к неуправляемому заглушки.|  
|`STUBFRAME_U2M`|Заглушки неуправляемого в управляемый фрейм.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Переход между доменами приложений.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Вызов упрощенного метода.|  
|`STUBFRAME_FUNC_EVAL`|Начало вычисления функции.|  
|`STUBFRAME_INTERNALCALL`|Внутренний вызов в среду.|  
|`STUBFRAME_CLASS_INIT`|Начало инициализации класса.|  
|`STUBFRAME_EXCEPTION`|Исключение, создается исключение.|  
|`STUBFRAME_SECURITY`|Фрейм, используемый для управления доступом для кода.|  
|`STUBFRAME_JIT_COMPILATION`|Среда выполнения выполняет JIT-компиляцию метода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
