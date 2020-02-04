---
title: Метод ICorDebugMutableDataTarget::SetThreadContext
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 063c7954543174caece6f3dcbe005a4b2d059c64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792848"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Метод ICorDebugMutableDataTarget::SetThreadContext
Задает контекст (значения регистра) для потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwThreadID`  
 [in] Идентификатор потока, определяемый операционной системой.  
  
 `contextSize`  
 [in] Размер буфера `pContext` для записи.  
  
 `pContext`  
 [in] Указатель на байты, которые требуется записать.  
  
## <a name="remarks"></a>Заметки  
 Метод `SetThreadContext` обновляет текущий контекст для потока, указанного аргументом `dwThreadID`, который задается операционной системой. Формат записи контекста определяется платформой, указанной в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) . В Windows это структура [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
