---
title: "Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Метод ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Поддерживается в [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] и более поздних версиях]  
  
 Включает или отключает определенные типы [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Примечания  
 Если `enableExceptionsOutsideOfJMC` имеет значение `false`:  
  
-   Исключение DEBUG_EXCEPTION_FIRST_CHANCE не приведет к с помощью обратного вызова отладчика.  
  
-   Исключение DEBUG_EXCEPTION_CATCH_HANDLER_FOUND не приведет обратный вызов в отладчик, если исключение никогда не попадает в пользовательский код (то есть путь от источника исключения в обработчик исключений не имеет методов помеченных как JustMyCode или JMC).  
  
 Значением свойства `enableExceptionsOutsideOfJMC` по умолчанию является `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess8](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
