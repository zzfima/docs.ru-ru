---
title: Интерфейс ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791879"
---
# <a name="icordebugstackwalk-interface"></a>Интерфейс ICorDebugStackWalk
Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetContext](icordebugstackwalk-getcontext-method.md)|Возвращает контекст для текущего кадра в объекте `ICorDebugStackWalk`.|  
|[Метод SetContext](icordebugstackwalk-setcontext-method.md)|Задает в качестве текущего контекста объекта `ICorDebugStackWalk` допустимый контекст для потока.|  
|[Метод Next](icordebugstackwalk-next-method.md)|Перемещает объект `ICorDebugStackWalk` в следующий кадр.|  
|[Метод GetFrame](icordebugstackwalk-getframe-method.md)|Возвращает текущий кадр в объекте `ICorDebugStackWalk`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
