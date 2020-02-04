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
ms.openlocfilehash: fdaad46b739721ff95b712d4b6461a793ae0a480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791421"
---
# <a name="icordebugthread2-interface"></a>Интерфейс ICorDebugThread2
Служит логическим расширением интерфейса ICorDebugThread.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)|Возвращает массив экземпляров COR_ACTIVE_FUNCTION, содержащих данные об активных функциях в кадрах потока.|  
|[Метод GetConnectionID](icordebugthread2-getconnectionid-method.md)|Возвращает идентификатор подключения для этого `ICorDebugThread2`.|  
|[Метод GetTaskID](icordebugthread2-gettaskid-method.md)|Возвращает идентификатор задачи для этого `ICorDebugThread2`.|  
|[Метод GetVolatileOSThreadID](icordebugthread2-getvolatileosthreadid-method.md)|Возвращает идентификатор потока операционной системы для этого `ICorDebugThread2`.|  
|[Метод InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md)|Позволяет отладчику перехватывать текущее исключение в потоке.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
