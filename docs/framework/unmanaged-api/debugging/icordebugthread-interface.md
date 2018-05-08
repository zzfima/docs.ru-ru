---
title: ICorDebugThread интерфейс1
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
ms.openlocfilehash: 404f1bdf5865733648084e34a558b7b20a59b3ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread интерфейс1
Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает в данном `ICorDebugThread`.|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, который позволяет проходить через активного кадра, в этом `ICorDebugThread`.|  
|[Метод EnumerateChains](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель ICorDebugChainEnum, содержащий всех цепочек стека в этом `ICorDebugThread`.|  
|[Метод GetActiveChain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Возвращает указатель на интерфейс для активного ICorDebugChain в данном `ICorDebugThread`.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Возвращает указатель на интерфейс для активного ICorDebugFrame в данном `ICorDebugThread`.|  
|[Метод GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Возвращает указатель на интерфейс в домен приложения, в котором `ICorDebugThread` в данный момент.|  
|[Метод GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Получает указатель интерфейса на объект ICorDebugValue, представляющий исключение в настоящее время в управляемом коде.|  
|[Метод GetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Возвращает значение CorDebugThreadState, описывающее текущее состояние отладки данного `ICorDebugThread`.|  
|[Метод GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Возвращает текущий дескриптор для активной части это `ICorDebugThread`.|  
|[Метод GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы активной части это `ICorDebugThread`.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Возвращает указатель на интерфейс среды выполнения (CLR) потоку выполнения.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Возвращает указатель интерфейса, для которого данный процесс `ICorDebugThread` эти формы.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Получает указатель интерфейса на набор регистров, связанных с этим `ICorDebugThread`.|  
|[Метод GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Возвращает поразрядное сочетание значений CorDebugUserState, описывающих текущее состояние данного объекта `ICorDebugThread`.|  
|[Метод SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание `CorDebugThreadState` значения, описывающие состояние отладки данного `ICorDebugThread`.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
