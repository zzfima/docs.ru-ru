---
title: Метод ICorDebugManagedCallback2::MDANotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131462"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="7005f-102">Метод ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="7005f-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="7005f-103">Предоставляет уведомление о том, что при выполнении кода в отлаживаемом приложении обнаружен управляемый помощник по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="7005f-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7005f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7005f-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7005f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7005f-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="7005f-106">окне Указатель на интерфейс ICorDebugController, предоставляющий процесс или домен приложения, в котором выполнялся MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="7005f-107">Отладчик не должен делать никаких предположений относительно того, является ли контроллер процессом или доменом приложения, хотя он всегда может запрашивать интерфейс для выполнения определения.</span><span class="sxs-lookup"><span data-stu-id="7005f-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7005f-108">окне Указатель на интерфейс ICorDebugThread, предоставляющий управляемый поток, в котором произошло событие отладки.</span><span class="sxs-lookup"><span data-stu-id="7005f-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="7005f-109">Если MDA произошло в неуправляемом потоке, значение `pThread` будет равно null.</span><span class="sxs-lookup"><span data-stu-id="7005f-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="7005f-110">Необходимо получить идентификатор потока операционной системы (ОС) из самого объекта MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="7005f-111">окне Указатель на интерфейс [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) , предоставляющий сведения об MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7005f-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="7005f-112">Remarks</span></span>  
 <span data-ttu-id="7005f-113">MDA является эвристическим предупреждением и не требует явных действий отладчика, за исключением вызова [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="7005f-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="7005f-114">Общеязыковая среда выполнения (CLR) может определять, какие MDA срабатывают и какие данные находятся в любом заданном MDA в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="7005f-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="7005f-115">Таким образом, отладчики не должны создавать функции, требующие специальных шаблонов MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="7005f-116">Помощники MDA могут быть поставлены в очередь и срабатывать вскоре после обнаружения помощника по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7005f-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="7005f-117">Это может произойти, если среде выполнения необходимо подождать, пока она достигнет надежной точки для запуска MDA, вместо того, чтобы использовать MDA при обнаружении.</span><span class="sxs-lookup"><span data-stu-id="7005f-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="7005f-118">Это также означает, что среда выполнения может запустить несколько MDA в одном наборе обратных вызовов в очереди (аналогично операции "присоединение").</span><span class="sxs-lookup"><span data-stu-id="7005f-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="7005f-119">Отладчик должен освободить ссылку на экземпляр `ICorDebugMDA` сразу после возврата из обратного вызова `MDANotification`, чтобы разрешить среде CLR перезапустить память, занятую MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="7005f-120">Освобождение экземпляра может повысить производительность при срабатывании многих MDA.</span><span class="sxs-lookup"><span data-stu-id="7005f-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7005f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7005f-121">Requirements</span></span>  
 <span data-ttu-id="7005f-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7005f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7005f-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7005f-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7005f-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7005f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7005f-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7005f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7005f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7005f-126">See also</span></span>

- [<span data-ttu-id="7005f-127">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="7005f-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7005f-128">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="7005f-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7005f-129">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7005f-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
