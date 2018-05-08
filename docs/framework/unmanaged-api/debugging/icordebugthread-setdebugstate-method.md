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
ms.openlocfilehash: ada120b9cb4100bfadff83d96e0226f911958bf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadsetdebugstate-method"></a>Метод ICorDebugThread::SetDebugState
Задает флаги, описывающие состояние отладки ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `state`  
 [in] Побитовое сочетание значений перечисления CorDebugThreadState, которые определяют состояние отладки для данного потока.  
  
## <a name="remarks"></a>Примечания  
 `SetDebugState` Задает текущее состояние отладки потока. («Текущее состояние отладки» представляет состояние отладки, будто процесс будет продолжен, а не фактический текущее состояние.) Нормальное значение для этого является THREAD_RUNNING. Только отладчик может повлиять на состояние отладки потока. Состояния отладки продолжений наступают последними, поэтому если вы хотите сохранить поток продолжает THREAD_SUSPEND для нескольких, можно задать его один раз и после этого не нужно беспокоиться о нем. Приостановка потоков и возобновление процесса может вызвать взаимоблокировки, хотя обычно маловероятно. Это встроенная функция качества потоков и процессов, путем разработки. Отладчик может асинхронно прерывание и возобновление потоков для устранения взаимоблокировки. Если состояние пользователя потока включает в себя USER_UNSAFE_POINT, поток может заблокировать сбора мусора (GC). Это означает, что поток имеет гораздо выше вероятность взаимоблокировки. Это может не повлиять на "Отладка" события уже поставлено в очередь. Таким образом отладчик должен расходования всего события очереди (путем вызова [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) перед Приостановка или возобновление работы потоков. В противном случае он может получать события в потоке, который он полагает, что он уже приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
