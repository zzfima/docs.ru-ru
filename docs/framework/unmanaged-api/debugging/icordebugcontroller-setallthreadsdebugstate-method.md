---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ee396c512dca2bea0a7a9737d5515defce4b2b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>Метод ICorDebugController::SetAllThreadsDebugState
Задает состояние отладки все управляемые потоки в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `state`  
 [in] Значение перечисления «CorDebugThreadState», которое указывает состояние потока для отладки.  
  
 `pExceptThisThread`  
 [in] Указатель на объект «ICorDebugThread», представляющий поток, исключенные из параметра состояние отладки. Если это значение равно null, ни один поток не исключен.  
  
## <a name="remarks"></a>Примечания  
 `SetAllThreadsDebugState` Метод может повлиять на потоки, которые не видны через [метод EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), поэтому потоков, которые были приостановлены с `SetAllThreadsDebugState` метод должен будет возобновлена с `SetAllThreadsDebugState` метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
