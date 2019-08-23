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
ms.openlocfilehash: 1517d686c50923f5599e33436e0ad6126e8be140
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923145"
---
# <a name="icordebugthread-interface"></a>Интерфейс ICorDebugThread
Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает с этим `ICorDebugThread`объектом.|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом `ICorDebugThread`объекте.|  
|[Метод EnumerateChains](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в `ICorDebugThread`этом.|  
|[Метод GetActiveChain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Возвращает указатель интерфейса на активный ICorDebugChain для этого `ICorDebugThread`объекта.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread`.|  
|[Метод GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, в котором `ICorDebugThread` выполняется в данный момент.|  
|[Метод GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.|  
|[Метод GetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки этого `ICorDebugThread`объекта.|  
|[Метод GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Возвращает текущий обработчик для активной части этого `ICorDebugThread`объекта.|  
|[Метод GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы активной части `ICorDebugThread`.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Возвращает указатель интерфейса на поток среды CLR.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Возвращает указатель интерфейса для процесса, частью которого является эта `ICorDebugThread` форма.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread`.|  
|[Метод GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого `ICorDebugThread`объекта.|  
|[Метод SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание `CorDebugThreadState` значений, описывающих состояние отладки этого `ICorDebugThread`объекта.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
