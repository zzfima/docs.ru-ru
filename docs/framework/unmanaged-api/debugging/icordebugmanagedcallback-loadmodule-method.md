---
title: Метод ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbf538f066058b4f80d8cfd6cdf1a79683c79be9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a>Метод ICorDebugManagedCallback::LoadModule
Уведомляет отладчик успешно загружен общих модуля среды CLR (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которую был загружен модуль.  
  
 `pModule`  
 [in] Указатель на объект ICorDebugModule, который представляет модуль среды CLR.  
  
## <a name="remarks"></a>Примечания  
 `LoadModule` Обратный вызов обеспечивает подходящее время для просмотра метаданных для модуля, задать флаги компилятора just-in-time (JIT), или включить или отключить обратные вызовы для модуля загрузки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод UnloadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
