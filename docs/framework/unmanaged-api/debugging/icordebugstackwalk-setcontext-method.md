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
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131814"
---
# <a name="icordebugstackwalksetcontext-method"></a>Метод ICorDebugStackWalk::SetContext
Задает для текущего контекста объекта [икордебугстакквалк](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) допустимый контекст для потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `flag`  
 окне Флаг [кордебугсетконтекстфлаг](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) , который указывает, относится ли контекст к активному кадру в стеке или к контексту, полученному путем очистки стека.  
  
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
  
 Вы можете получить точную побитовую копию этого контекста путем немедленного вызова метода [икордебугстакквалк:: oncontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
