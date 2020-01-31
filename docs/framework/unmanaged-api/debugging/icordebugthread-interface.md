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
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791473"
---
# <a name="icordebugthread-interface"></a>Интерфейс ICorDebugThread
Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](icordebugthread-clearcurrentexception-method.md)|Этот метод не реализован. Не используйте его.|  
|[Метод CreateEval](icordebugthread-createeval-method.md)|Создает объект ICorDebugEval, который работает на этом `ICorDebugThread`.|  
|[Метод CreateStepper](icordebugthread-createstepper-method.md)|Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом `ICorDebugThread`.|  
|[Метод EnumerateChains](icordebugthread-enumeratechains-method.md)|Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом `ICorDebugThread`.|  
|[Метод GetActiveChain](icordebugthread-getactivechain-method.md)|Возвращает указатель интерфейса на активный ICorDebugChain для этого `ICorDebugThread`.|  
|[Метод GetActiveFrame](icordebugthread-getactiveframe-method.md)|Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread`.|  
|[Метод GetAppDomain](icordebugthread-getappdomain-method.md)|Возвращает указатель интерфейса на домен приложения, в котором выполняется эта `ICorDebugThread`.|  
|[Метод GetCurrentException](icordebugthread-getcurrentexception-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.|  
|[Метод GetDebugState](icordebugthread-getdebugstate-method.md)|Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки данного `ICorDebugThread`.|  
|[Метод GetHandle](icordebugthread-gethandle-method.md)|Возвращает текущий маркер для активной части этого `ICorDebugThread`.|  
|[Метод GetID](icordebugthread-getid-method.md)|Возвращает идентификатор текущей операционной системы активной части этого `ICorDebugThread`.|  
|[Метод GetObject](icordebugthread-getobject-method.md)|Возвращает указатель интерфейса на поток среды CLR.|  
|[Метод GetProcess](icordebugthread-getprocess-method.md)|Возвращает указатель интерфейса на процесс, в котором эта `ICorDebugThread` образует часть.|  
|[Метод GetRegisterSet](icordebugthread-getregisterset-method.md)|Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread`.|  
|[Метод GetUserState](icordebugthread-getuserstate-method.md)|Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого `ICorDebugThread`.|  
|[Метод SetDebugState](icordebugthread-setdebugstate-method.md)|Задает побитовое сочетание значений `CorDebugThreadState`, описывающих состояние отладки этого `ICorDebugThread`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
