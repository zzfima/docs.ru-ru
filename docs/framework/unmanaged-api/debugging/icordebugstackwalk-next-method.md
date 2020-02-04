---
title: Метод ICorDebugStackWalk::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791869"
---
# <a name="icordebugstackwalknext-method"></a>Метод ICorDebugStackWalk::Next
Перемещает объект [икордебугстакквалк](icordebugstackwalk-interface.md) в следующий кадр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Среда выполнения успешно развернута до следующего кадра (см. примечания).|  
|E_FAIL|Объект `ICorDebugStackWalk` не может быть расширен.|  
|CORDBG_S_AT_END_OF_STACK|В результате этого очистки достигнут конец стека.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Метод `Next` перемещает объект `ICorDebugStackWalk` в вызывающий кадр только в том случае, если среда выполнения может очистить текущий кадр. В противном случае объект переходит к следующему кадру, который среда выполнения может очистить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
