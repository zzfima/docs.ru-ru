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
ms.openlocfilehash: 48f1b485b6dfa8fd898f6ea00eee2d7b397deba6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131861"
---
# <a name="icordebugstackwalk-interface"></a>Интерфейс ICorDebugStackWalk
Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Возвращает контекст для текущего кадра в объекте `ICorDebugStackWalk`.|  
|[Метод SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Задает в качестве текущего контекста объекта `ICorDebugStackWalk` допустимый контекст для потока.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Перемещает объект `ICorDebugStackWalk` в следующий кадр.|  
|[Метод GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Возвращает текущий кадр в объекте `ICorDebugStackWalk`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
