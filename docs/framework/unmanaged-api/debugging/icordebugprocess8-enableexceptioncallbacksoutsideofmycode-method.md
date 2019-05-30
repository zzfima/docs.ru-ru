---
title: Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52a58f75ca7abd1bd1f871bcf4637bfd7eb7bdcd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300543"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Поддерживается в .NET Framework 4.6 и более поздних версиях]  
  
 Включает или отключает определенные виды [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Примечания  
 Если `enableExceptionsOutsideOfJMC` имеет значение `false`:  
  
- Исключение DEBUG_EXCEPTION_FIRST_CHANCE не приведет к обратный вызов к отладчику.  
  
- Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не произойдет обратный вызов на отладчик Если исключение никогда не попадает в пользовательский код (то есть путь от источника исключения в обработчик исключений имеет нет методов, помеченных как JustMyCode или JMC).  
  
 Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess8](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
