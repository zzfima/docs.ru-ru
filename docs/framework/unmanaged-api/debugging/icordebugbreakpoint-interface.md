---
title: Интерфейс ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122801"
---
# <a name="icordebugbreakpoint-interface"></a>Интерфейс ICorDebugBreakpoint

Представляет точку останова в функции или точку контрольного значения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Activate](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Задает активное состояние этого `ICorDebugBreakpoint`.|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Возвращает значение, указывающее, активна ли эта `ICorDebugBreakpoint`.|  
  
## <a name="remarks"></a>Заметки  
 Точки останова не поддерживают непосредственно условные выражения. Если требуется такая функциональность, отладчик должен реализовать его поверх `ICorDebugBreakpoint`.  
  
 Интерфейс ICorDebugFunctionBreakpoint расширяет `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
