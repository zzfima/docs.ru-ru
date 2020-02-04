---
title: Метод ICorDebugStackWalk::SetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791857"
---
# <a name="icordebugstackwalksetcontext-method"></a>Метод ICorDebugStackWalk::SetContext
Задает для текущего контекста объекта [икордебугстакквалк](icordebugstackwalk-interface.md) допустимый контекст для потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `flag`  
 окне Флаг [кордебугсетконтекстфлаг](cordebugsetcontextflag-enumeration.md) , который указывает, относится ли контекст к активному кадру в стеке или к контексту, полученному путем очистки стека.  
  
 `contextSize`  
 окне Выделенный размер буфера `CONTEXT`.  
  
 `context`  
 окне Буфер `CONTEXT`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Контекст объекта `ICorDebugStackWalk` был успешно задан.|  
|E_FAIL|Контекст объекта `ICorDebugStackWalk` не задан.|  
|E_INVALIDARG|Контекст имеет значение null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Буфер контекста слишком мал.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Этот метод не изменяет текущий контекст потока.  
  
 Установка текущего контекста в недопустимый контекст может привести к непредсказуемым результатам обхода стека.  
  
 Вы можете получить точную побитовую копию этого контекста путем немедленного вызова метода [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
