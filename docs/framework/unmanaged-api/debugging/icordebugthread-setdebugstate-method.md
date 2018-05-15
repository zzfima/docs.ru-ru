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
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="4ad6a-102">Метод ICorDebugThread::SetDebugState</span><span class="sxs-lookup"><span data-stu-id="4ad6a-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="4ad6a-103">Задает флаги, описывающие состояние отладки ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ad6a-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ad6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ad6a-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="4ad6a-106">[in] Побитовое сочетание значений перечисления CorDebugThreadState, которые определяют состояние отладки для данного потока.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ad6a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ad6a-107">Remarks</span></span>  
 <span data-ttu-id="4ad6a-108">`SetDebugState` Задает текущее состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="4ad6a-109">(«Текущее состояние отладки» представляет состояние отладки, будто процесс будет продолжен, а не фактический текущее состояние.) Нормальное значение для этого является THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="4ad6a-110">Только отладчик может повлиять на состояние отладки потока.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="4ad6a-111">Состояния отладки продолжений наступают последними, поэтому если вы хотите сохранить поток продолжает THREAD_SUSPEND для нескольких, можно задать его один раз и после этого не нужно беспокоиться о нем.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="4ad6a-112">Приостановка потоков и возобновление процесса может вызвать взаимоблокировки, хотя обычно маловероятно.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="4ad6a-113">Это встроенная функция качества потоков и процессов, путем разработки.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="4ad6a-114">Отладчик может асинхронно прерывание и возобновление потоков для устранения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="4ad6a-115">Если состояние пользователя потока включает в себя USER_UNSAFE_POINT, поток может заблокировать сбора мусора (GC).</span><span class="sxs-lookup"><span data-stu-id="4ad6a-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="4ad6a-116">Это означает, что поток имеет гораздо выше вероятность взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="4ad6a-117">Это может не повлиять на "Отладка" события уже поставлено в очередь.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="4ad6a-118">Таким образом отладчик должен расходования всего события очереди (путем вызова [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) перед Приостановка или возобновление работы потоков.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="4ad6a-119">В противном случае он может получать события в потоке, который он полагает, что он уже приостановлен.</span><span class="sxs-lookup"><span data-stu-id="4ad6a-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad6a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4ad6a-120">Requirements</span></span>  
 <span data-ttu-id="4ad6a-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ad6a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad6a-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ad6a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ad6a-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ad6a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad6a-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad6a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
