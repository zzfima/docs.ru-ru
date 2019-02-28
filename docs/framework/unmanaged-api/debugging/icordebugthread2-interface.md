---
title: Интерфейс ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e162c114de013eed160a515dbc92fef47ea3327
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980507"
---
# <a name="icordebugthread2-interface"></a>Интерфейс ICorDebugThread2
Служит логическим расширением ICorDebugThread-интерфейс.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.|  
|[Метод GetConnectionID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|Получает идентификатор подключения для данного `ICorDebugThread2`.|  
|[Метод GetTaskID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|Получает идентификатор задачи для данного `ICorDebugThread2`.|  
|[Метод GetVolatileOSThreadID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|Получает идентификатор потока операционной системы для данного `ICorDebugThread2`.|  
|[Метод InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|Позволяет отладчику перехватить текущее исключение в потоке.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
