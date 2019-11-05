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
ms.openlocfilehash: 1b2f3feca15bb8add17c9fe70805347b7c6a48ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133427"
---
# <a name="icordebugthreadsetdebugstate-method"></a>Метод ICorDebugThread::SetDebugState
Устанавливает флаги, описывающие состояние отладки этого ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `state`  
 окне Побитовое сочетание значений перечисления Кордебугсреадстате, определяющих состояние отладки этого потока.  
  
## <a name="remarks"></a>Заметки  
 `SetDebugState` задает текущее состояние отладки потока. ("Текущее состояние отладки" представляет состояние отладки, если процесс должен быть продолжен, а не фактическое текущее состояние.) Нормальное значение для этого параметра — THREAD_RUN. Только отладчик может повлиять на состояние отладки потока. Состояния отладки продолжают выполняться, поэтому, если вы хотите, чтобы поток THREAD_SUSPENDed над несколькими, вы можете установить его один раз, а затем не беспокоиться о нем. Приостановка потоков и возобновление процесса могут привести к взаимоблокировке, хотя обычно маловероятно. Это встроенное качество потоков и процессов, а именно-проектирование. Отладчик может асинхронно приостанавливать и возобновлять потоки, чтобы нарушить взаимоблокировку. Если пользовательское состояние потока включает USER_UNSAFE_POINT, поток может блокировать сборку мусора (GC). Это означает, что приостановленный поток имеет намного более высокий шанс возникновения взаимоблокировки. Это может не влиять на события отладки, уже поставленные в очередь. Таким образом, отладчик должен очистить всю очередь событий (вызвав [ICorDebugController:: хаскуеуедкаллбаккс](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) перед приостановкой или возобновлением потоков. В противном случае он может получить события в потоке, который предположительно уже приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
