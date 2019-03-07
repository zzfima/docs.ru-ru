---
title: Метод ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0baecc56df18a8ce346f5c4a9f52dd4006583867
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476403"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a>Метод ICorDebugManagedCallback::BreakpointSetError
Уведомляет отладчик о том, что среда CLR не удалось точно привязать точку останова, который был задан до функции just-in-time (JIT) компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит непривязанные точки останова.  
  
 `pThread`  
 [in] Указатель на ICorDebugThread объект, представляющий поток, который содержит непривязанные точки останова.  
  
 `pBreakpoint`  
 [in] Указатель на ICorDebugBreakpoint объект, представляющий непривязанные точки останова.  
  
 `dwError`  
 [in] Целое число, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Никогда не будет достигнута данной точки останова. Отладчик должен отключить и повторно привязать его.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
