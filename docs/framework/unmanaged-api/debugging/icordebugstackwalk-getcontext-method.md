---
title: Метод ICorDebugStackWalk::GetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782750"
---
# <a name="icordebugstackwalkgetcontext-method"></a>Метод ICorDebugStackWalk::GetContext
Возвращает контекст для текущего кадра в [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `contextFlags`  
 [in] Флаги, указывающие запрошенное содержимое буфера контекста (определяется в заголовке WinNT.h).  
  
 `contextBufSize`  
 [in] Выделенный размер буфера контекста.  
  
 `contextSize`  
 [out] Фактический размер контекста. Это значение должно быть меньше или равен размеру буфера контекста.  
  
 `contextBuf`  
 [out] Буфер контекста.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Контекст для текущего кадра успешно возвращен.|  
|E_FAIL|Контекст не может быть возвращено.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Буфер контекста слишком мал.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель кадра уже находится в конце стека; Таким образом может осуществляться без дополнительных кадров.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 Поскольку раскрутке восстанавливается только подмножество регистров, например неизменяемые регистры, контекст может не соответствовать состоянию регистра во время вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
