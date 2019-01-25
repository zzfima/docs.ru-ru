---
title: Метод ICorDebugUnmanagedCallback::DebugEvent
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fd07f018bdc5bd9fd8ca6a81b4aca6d6f97a531
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647300"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="1f814-102">Метод ICorDebugUnmanagedCallback::DebugEvent</span><span class="sxs-lookup"><span data-stu-id="1f814-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="1f814-103">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="1f814-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f814-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f814-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f814-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f814-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="1f814-106">[in] Указатель на собственный события.</span><span class="sxs-lookup"><span data-stu-id="1f814-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="1f814-107">[in] `true`, если взаимодействие с состоянием управляемого процесса невозможна после возникновения события неуправляемые, пока отладчик не вызовет [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="1f814-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f814-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f814-108">Remarks</span></span>  
 <span data-ttu-id="1f814-109">Если отлаживаемый поток является потоком Win32, не используйте ни с одним элементом Win32 интерфейса отладки.</span><span class="sxs-lookup"><span data-stu-id="1f814-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="1f814-110">Вы можете вызвать `ICorDebugController::Continue` только в потоке Win32 и только в том случае, если продолжение за-внешнее событие.</span><span class="sxs-lookup"><span data-stu-id="1f814-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="1f814-111">`DebugEvent` Обратного вызова не соответствуют стандартным правилам для обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="1f814-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="1f814-112">При вызове `DebugEvent`, процесс будет находиться в необработанный, состоянии остановки отладки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1f814-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="1f814-113">Процесс не будут синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="1f814-113">The process will not be synchronized.</span></span> <span data-ttu-id="1f814-114">Он автоматически войдет в синхронизированном состоянии, когда необходимо выполнить запрос сведений об управляемом коде, что может вызвать другие вложенные `DebugEvent` обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="1f814-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="1f814-115">Вызовите [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) на процесс, чтобы пропустить событие исключения, прежде чем продолжить процесс.</span><span class="sxs-lookup"><span data-stu-id="1f814-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="1f814-116">Вызов этого метода отправляет продолжения вместо DBG_EXCEPTION_NOT_HANDLED на запроса на продолжение, а также автоматически очищает-резервному точки останова и одношаговые исключения.</span><span class="sxs-lookup"><span data-stu-id="1f814-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="1f814-117">Out of band события могут поступать в любое время, даже в том случае, если отлаживаемого приложения останавливается, и необработанные события внутренней уже существует.</span><span class="sxs-lookup"><span data-stu-id="1f814-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="1f814-118">В .NET Framework версии 2.0 отладчик должен немедленно продолжить прошлое событие точки останова каналу.</span><span class="sxs-lookup"><span data-stu-id="1f814-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="1f814-119">Отладчик должен использовать [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) методы для добавления и удаления точки останова.</span><span class="sxs-lookup"><span data-stu-id="1f814-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="1f814-120">Эти методы будут автоматически пропускать все точки останова каналу.</span><span class="sxs-lookup"><span data-stu-id="1f814-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="1f814-121">Таким образом, точки останова только-каналу, отправить должно быть точками останова, которые уже находятся в потоке инструкций, например вызов Win32 `DebugBreak` функции.</span><span class="sxs-lookup"><span data-stu-id="1f814-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="1f814-122">Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), или другой элемент [API отладки](../../../../docs/framework/unmanaged-api/debugging/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f814-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f814-123">Требования</span><span class="sxs-lookup"><span data-stu-id="1f814-123">Requirements</span></span>  
 <span data-ttu-id="1f814-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f814-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f814-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f814-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f814-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f814-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f814-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f814-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f814-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1f814-128">See also</span></span>
- [<span data-ttu-id="1f814-129">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="1f814-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
