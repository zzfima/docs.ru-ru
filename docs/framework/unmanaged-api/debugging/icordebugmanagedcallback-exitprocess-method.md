---
title: Метод ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51162bfb6f9763d2ab4ac1f86e0ccdc15b601271
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159878"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Метод ICorDebugManagedCallback::ExitProcess
Уведомляет отладчик о том, что процесс завершен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 [in] Указатель на объект ICorDebugProcess, представляющий процесс.  
  
## <a name="remarks"></a>Примечания  
 Не удается продолжить выполнение после `ExitProcess` событий. Это событие вызывается асинхронно с другими событиями во время появится нужный процесс нужно остановить. Это может произойти, если процесс прерывается во время остановки, обычно вследствие внешних.  
  
 Если среда CLR (CLR), который уже обслуживается управляемом обратном вызове, это событие будет отложено до после возвращения ответного вызова.  
  
 `ExitProcess` Это единственное событие завершения и выгрузки, гарантированно вызывается при завершении работы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
