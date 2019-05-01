---
title: Метод ICorDebugThread::SetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987146"
---
# <a name="icordebugthreadsetdebugstate-method"></a>Метод ICorDebugThread::SetDebugState
Задает флаги, описывающие состояние отладки ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `state`  
 [in] Побитовое сочетание значений перечисления CorDebugThreadState, определяющие состояние отладки для данного потока.  
  
## <a name="remarks"></a>Примечания  
 `SetDebugState` Задает текущее состояние отладки потока. («Текущее состояние отладки» представляет состояние отладки, будто процесс будет продолжен, а не фактическое текущее состояние.) Нормальное значение для этого — THREAD_RUNNING. Только отладчик может повлиять на состояние отладки потока. Состояния отладки продолжений наступают последними, поэтому если вы хотите сохранить поток продолжает THREAD_SUSPEND для нескольких, можно установить значение один раз и после этого не нужно беспокоиться о нем. Приостановка потоков и возобновление процесса может вызвать взаимоблокировки, хотя обычно маловероятно. Это является характерным признаком качества потоков и процессов и структурой. Отладчик можно асинхронно прервать и возобновлять потоки для устранения взаимоблокировки. Если состояние пользователя потока включает в себя USER_UNSAFE_POINT, поток может заблокировать сбор мусора (GC). Это означает, что поток имеет гораздо выше вероятность взаимоблокировки. Это может не повлиять на "Отладка" события уже поставлено в очередь. Таким образом отладчик должен обеспечить утечку всего события очереди (путем вызова [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) перед Приостановка или возобновление работы потоков. В противном случае он может получать события в потоке, который считает уже приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
