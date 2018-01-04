---
title: "Метод ICorDebugUnmanagedCallback::DebugEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback.DebugEvent
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49c3386fcda0bc731935ec9db7d029d0e619ef14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="3a950-102">Метод ICorDebugUnmanagedCallback::DebugEvent</span><span class="sxs-lookup"><span data-stu-id="3a950-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="3a950-103">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="3a950-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a950-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a950-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a950-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a950-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="3a950-106">[in] Указатель на собственный событий.</span><span class="sxs-lookup"><span data-stu-id="3a950-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="3a950-107">[in] `true`, если невозможно взаимодействие с состоянием управляемого процесса после возникновения события неуправляемым, пока отладчик вызывает [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="3a950-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a950-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a950-108">Remarks</span></span>  
 <span data-ttu-id="3a950-109">Если отлаживаемый поток является потоком Win32, не используйте никакие элементы Win32 интерфейса отладки.</span><span class="sxs-lookup"><span data-stu-id="3a950-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="3a950-110">Можно вызвать `ICorDebugController::Continue` только потоком Win32 и только в том случае, если продолжение после события по каналу.</span><span class="sxs-lookup"><span data-stu-id="3a950-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="3a950-111">`DebugEvent` Обратного вызова не действуют стандартные правила для обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="3a950-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="3a950-112">При вызове `DebugEvent`, процесс будет находиться в необработанный, состоянии остановки отладки операционной Системой.</span><span class="sxs-lookup"><span data-stu-id="3a950-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="3a950-113">Процесс не будут синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="3a950-113">The process will not be synchronized.</span></span> <span data-ttu-id="3a950-114">Автоматически перейдет в состояние синхронизации при необходимости выполнить запрос для получения сведений об управляемом коде, что может стать причиной других вложенных `DebugEvent` обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="3a950-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="3a950-115">Вызовите [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) в процессе, чтобы пропустить событие исключения перед продолжением процесса.</span><span class="sxs-lookup"><span data-stu-id="3a950-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="3a950-116">Вызов этого метода отправляет продолжения вместо DBG_EXCEPTION_NOT_HANDLED продолжить запроса, а также автоматически очищает по каналу точки останова и пошагово исключения.</span><span class="sxs-lookup"><span data-stu-id="3a950-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="3a950-117">События по каналу могут поступать в любое время, даже в том случае, если останавливается отлаживаемого приложения и необработанные события по каналу уже существует.</span><span class="sxs-lookup"><span data-stu-id="3a950-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="3a950-118">В платформе .NET Framework версии 2.0 отладчик должен немедленно продолжить прошлое событие точки останова по каналу.</span><span class="sxs-lookup"><span data-stu-id="3a950-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="3a950-119">Отладчик должен использовать [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) методы для добавления и удаления точек останова.</span><span class="sxs-lookup"><span data-stu-id="3a950-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="3a950-120">Эти методы будут автоматически пропускать все точки останова по каналу.</span><span class="sxs-lookup"><span data-stu-id="3a950-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="3a950-121">Таким образом, только для аппаратного точки останова, которые отправить должно быть точками останова, которые уже находятся в поток инструкций, например вызов Win32 `DebugBreak` функции.</span><span class="sxs-lookup"><span data-stu-id="3a950-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="3a950-122">Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), или любого другого элемента [API отладки](../../../../docs/framework/unmanaged-api/debugging/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a950-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a950-123">Требования</span><span class="sxs-lookup"><span data-stu-id="3a950-123">Requirements</span></span>  
 <span data-ttu-id="3a950-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a950-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a950-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a950-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a950-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a950-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a950-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a950-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a950-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3a950-128">See Also</span></span>  
 [<span data-ttu-id="3a950-129">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="3a950-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
