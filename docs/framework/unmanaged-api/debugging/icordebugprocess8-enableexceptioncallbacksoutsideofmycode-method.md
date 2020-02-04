---
title: Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792171"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Поддерживается в .NET Framework 4,6 и более поздних версиях]  
  
 Включает или отключает определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Заметки  
 Если `enableExceptionsOutsideOfJMC` имеет значение `false`:  
  
- Исключение DEBUG_EXCEPTION_FIRST_CHANCE не будет приводить к обратному вызову отладчика.  
  
- Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не приводит к обратному вызову отладчика, если исключение никогда не попадает в пользовательский код (то есть путь от источника исключения в обработчик исключений не имеет методов, помеченных как JustMyCode или JMC).  
  
 Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
