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
ms.openlocfilehash: 66f60b2342b6ff64f1329cbe57032291d5139384
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770600"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="404b8-102">Метод ICorDebugThread::SetDebugState</span><span class="sxs-lookup"><span data-stu-id="404b8-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="404b8-103">Задает флаги, описывающие состояние отладки ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="404b8-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="404b8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="404b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="404b8-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="404b8-106">[in] Побитовое сочетание значений перечисления CorDebugThreadState, определяющие состояние отладки для данного потока.</span><span class="sxs-lookup"><span data-stu-id="404b8-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="404b8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="404b8-107">Remarks</span></span>  
 <span data-ttu-id="404b8-108">`SetDebugState` Задает текущее состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="404b8-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="404b8-109">(«Текущее состояние отладки» представляет состояние отладки, будто процесс будет продолжен, а не фактическое текущее состояние.) Нормальное значение для этого — THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="404b8-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="404b8-110">Только отладчик может повлиять на состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="404b8-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="404b8-111">Состояния отладки продолжений наступают последними, поэтому если вы хотите сохранить поток продолжает THREAD_SUSPEND для нескольких, можно установить значение один раз и после этого не нужно беспокоиться о нем.</span><span class="sxs-lookup"><span data-stu-id="404b8-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="404b8-112">Приостановка потоков и возобновление процесса может вызвать взаимоблокировки, хотя обычно маловероятно.</span><span class="sxs-lookup"><span data-stu-id="404b8-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="404b8-113">Это является характерным признаком качества потоков и процессов и структурой.</span><span class="sxs-lookup"><span data-stu-id="404b8-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="404b8-114">Отладчик можно асинхронно прервать и возобновлять потоки для устранения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="404b8-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="404b8-115">Если состояние пользователя потока включает в себя USER_UNSAFE_POINT, поток может заблокировать сбор мусора (GC).</span><span class="sxs-lookup"><span data-stu-id="404b8-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="404b8-116">Это означает, что поток имеет гораздо выше вероятность взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="404b8-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="404b8-117">Это может не повлиять на "Отладка" события уже поставлено в очередь.</span><span class="sxs-lookup"><span data-stu-id="404b8-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="404b8-118">Таким образом отладчик должен обеспечить утечку всего события очереди (путем вызова [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) перед Приостановка или возобновление работы потоков.</span><span class="sxs-lookup"><span data-stu-id="404b8-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="404b8-119">В противном случае он может получать события в потоке, который считает уже приостановлен.</span><span class="sxs-lookup"><span data-stu-id="404b8-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="404b8-120">Требования</span><span class="sxs-lookup"><span data-stu-id="404b8-120">Requirements</span></span>  
 <span data-ttu-id="404b8-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404b8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404b8-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="404b8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="404b8-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="404b8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="404b8-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404b8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
