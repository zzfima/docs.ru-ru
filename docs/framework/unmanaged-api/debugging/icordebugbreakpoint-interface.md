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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784378"
---
# <a name="icordebugbreakpoint-interface"></a>Интерфейс ICorDebugBreakpoint

Представляет точку останова в функции или точку контрольного значения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Activate](icordebugbreakpoint-activate-method.md)|Задает активное состояние этого `ICorDebugBreakpoint`.|  
|[Метод IsActive](icordebugbreakpoint-isactive-method.md)|Возвращает значение, указывающее, активна ли эта `ICorDebugBreakpoint`.|  
  
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
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
