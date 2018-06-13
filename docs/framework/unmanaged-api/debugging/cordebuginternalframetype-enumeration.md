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
ms.openlocfilehash: 49b42a7fc54af56149b602b337e4a6c853c270cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406361"
---
# <a name="cordebuginternalframetype-enumeration"></a>Перечисление CorDebugInternalFrameType
Указывает тип кадра стека. Это перечисление используется методом [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) метод.  
  
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
  
|Член|Описание|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Значение Null. `ICorDebugInternalFrame::GetFrameType` Метод никогда не возвращает это значение.|  
|`STUBFRAME_M2U`|Кадр управляемый в неуправляемый заглушки.|  
|`STUBFRAME_U2M`|Кадр неуправляемый в управляемый заглушки.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Переход между доменами приложений.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Вызов облегченного метода.|  
|`STUBFRAME_FUNC_EVAL`|Начало вычисления функции.|  
|`STUBFRAME_INTERNALCALL`|Внутренний вызов в среду.|  
|`STUBFRAME_CLASS_INIT`|Начало инициализации класса.|  
|`STUBFRAME_EXCEPTION`|Исключение, создается исключение.|  
|`STUBFRAME_SECURITY`|Кадр, используемый для управления доступом для кода.|  
|`STUBFRAME_JIT_COMPILATION`|Среда выполнения выполняет JIT-компиляцию метода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
