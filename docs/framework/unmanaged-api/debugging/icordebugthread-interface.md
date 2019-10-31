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
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133496"
---
# <a name="icordebugthread-interface"></a>Интерфейс ICorDebugThread
Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает на этом `ICorDebugThread`.|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом `ICorDebugThread`.|  
|[Метод EnumerateChains](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом `ICorDebugThread`.|  
|[Метод GetActiveChain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Возвращает указатель интерфейса на активный ICorDebugChain для этого `ICorDebugThread`.|  
|[Метод GetActiveFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread`.|  
|[Метод GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, в котором выполняется эта `ICorDebugThread`.|  
|[Метод GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.|  
|[Метод GetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки данного `ICorDebugThread`.|  
|[Метод GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Возвращает текущий маркер для активной части этого `ICorDebugThread`.|  
|[Метод GetId](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы активной части этого `ICorDebugThread`.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Возвращает указатель интерфейса на поток среды CLR.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Возвращает указатель интерфейса на процесс, в котором эта `ICorDebugThread` образует часть.|  
|[Метод GetRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread`.|  
|[Метод GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого `ICorDebugThread`.|  
|[Метод SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание значений `CorDebugThreadState`, описывающих состояние отладки этого `ICorDebugThread`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
