---
title: Метод ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122029"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>Метод ICorDebugDataTarget::GetThreadContext
Возвращает текущий контекст потока для указанного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwThreadID`  
 окне Идентификатор потока, контекст которого должен быть получен. Идентификатор определяется операционной системой.  
  
 `contextFlags`  
 окне Побитовое сочетание флагов, зависящих от платформы, которые указывают, какие части контекста должны считываться.  
  
 `contextSize`  
 [входной] Размер `pContext`.  
  
 `pContext`  
 заполняет Буфер, в котором будет храниться контекст потока.  
  
## <a name="remarks"></a>Заметки  
 На платформах Windows `pContext` должен быть структурой `CONTEXT` (определенной в WinNT. h), подходящей для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) . `contextFlags` должны иметь те же значения, что и поле `ContextFlags` структуры `CONTEXT`. Структура `CONTEXT` зависит от процессора; Дополнительные сведения см. в файле WinNT. h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
