---
title: Интерфейс ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124065"
---
# <a name="icordebugframe-interface"></a>Интерфейс ICorDebugFrame

Представляет кадр текущего стека.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Возвращает объект ICorDebugStepper для выполнения операций с заходом относительно этого `ICorDebugFrame`.|  
|[Метод GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.|  
|[Метод GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внешняя рамка в цепочке.|  
|[Метод GetChain](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Возвращает указатель на ICorDebugChain, частью которого является этот `ICorDebugFrame`.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.|  
|[Метод GetFunctionToken](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.|  
|[Метод GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Возвращает диапазон абсолютных адресов кадра стека, представленного данным `ICorDebugFrame`.|  
  
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
