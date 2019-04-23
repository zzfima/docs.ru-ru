---
title: Интерфейс ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184708"
---
# <a name="icordebugthread-interface"></a>Интерфейс ICorDebugThread
Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает на этом `ICorDebugThread`.|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, который позволяет пошаговое выполнение активного кадра в этом `ICorDebugThread`.|  
|[Метод EnumerateChains](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель ICorDebugChainEnum, содержащий всех цепочек стека в этом `ICorDebugThread`.|  
|[Метод GetActiveChain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Получает указатель интерфейса на active ICorDebugChain об этом `ICorDebugThread`.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Получает указатель интерфейса на active ICorDebugFrame об этом `ICorDebugThread`.|  
|[Метод GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Получает указатель интерфейса на домен приложения, в котором этот `ICorDebugThread` в данный момент.|  
|[Метод GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Получает указатель на интерфейс ICorDebugValue объект, представляющий исключение в настоящее время в управляемом коде.|  
|[Метод GetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Возвращает значение CorDebugThreadState, описывающее текущее состояние отладки это `ICorDebugThread`.|  
|[Метод GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Получает текущий дескриптор для активной части это `ICorDebugThread`.|  
|[Метод GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы, активной части это `ICorDebugThread`.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Получает указатель интерфейса среды выполнения (CLR) потоку выполнения.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Получает указатель интерфейса, для которого данный процесс `ICorDebugThread` формы.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Получает указатель интерфейса на набор регистров, связанных с этим `ICorDebugThread`.|  
|[Метод GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Возвращает побитовое сочетание CorDebugUserState значения, описывающие текущее состояние данного объекта `ICorDebugThread`.|  
|[Метод SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание `CorDebugThreadState` значения, описывающие состояние отладки это `ICorDebugThread`.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
