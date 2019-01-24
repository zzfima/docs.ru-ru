---
title: Интерфейс1 ICorDebugFrame
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f160612e499ca7bd2185c95aa07a3784c5a4a19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635758"
---
# <a name="icordebugframe-interface1"></a>Интерфейс1 ICorDebugFrame
Представляет кадр текущего стека.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод CreateStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Получает ICorDebugStepper осуществлять пошаговое выполнение операций относительно данного `ICorDebugFrame`.|  
|[Метод GetCallee](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепи, что вызван этот кадр или возвращает значение null, если данный является самой внутренней рамке в цепочке.|  
|[Метод GetCaller](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепи, вызван этот кадр или возвращает значение null, если данный является самым крайним кадром в цепочке.|  
|[Метод GetChain](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Возвращает указатель на ICorDebugChain это `ICorDebugFrame` является частью.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Возвращает указатель на интерфейс ICorDebugCode, связанный с данным кадром стека.|  
|[Метод GetFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Возвращает указатель на ICorDebugFunction, который содержит код, связанный с данным кадром стека.|  
|[Метод GetFunctionToken](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Получает маркер метаданных для функции, которая содержит код, связанный с данным кадром стека.|  
|[Метод GetStackRange](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Возвращает диапазон абсолютных адресов кадра стека, представленный этим `ICorDebugFrame`.|  
  
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
