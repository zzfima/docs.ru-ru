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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133486"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="76498-102">Метод ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="76498-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="76498-103">Предоставляет уведомление, что выполнение кода обнаружил помощник по отладке управляемого (кода MDA) в отлаживаемом приложении.</span><span class="sxs-lookup"><span data-stu-id="76498-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76498-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76498-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76498-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76498-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="76498-106">[in] Указатель на интерфейс ICorDebugController, предоставляющей процесса или домена приложения, в котором произошло MDA.</span><span class="sxs-lookup"><span data-stu-id="76498-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="76498-107">Отладчик не следует вносить никаких предположений о том, является ли контроллер процесс или домен приложения, несмотря на то, что он всегда может запросить интерфейс принимать решения.</span><span class="sxs-lookup"><span data-stu-id="76498-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="76498-108">[in] Указатель на интерфейс ICorDebugThread, который предоставляет управляемый поток, в котором произошло событие отладки.</span><span class="sxs-lookup"><span data-stu-id="76498-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="76498-109">Если произошла по отладке управляемого кода в неуправляемый поток, значение `pThread` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="76498-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="76498-110">Из самого объекта по отладке управляемого кода необходимо получить идентификатор потока операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="76498-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="76498-111">[in] Указатель на [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) интерфейс, предоставляющий сведения по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="76498-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76498-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="76498-112">Remarks</span></span>  
 <span data-ttu-id="76498-113">MDA — это эвристическое предупреждение и не требует никаких действий явные отладчика, за исключением вызова [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) возобновить выполнение отлаживаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="76498-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="76498-114">Среда CLR (CLR) можно определить MDA, и какие данные оказываются в любой данный MDA, в любой момент.</span><span class="sxs-lookup"><span data-stu-id="76498-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="76498-115">Таким образом отладчики не должны строить любые функции, требующие определенных шаблонов по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="76498-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="76498-116">Помощники отладки управляемого кода в очередь и вызывать сразу же после обнаружения.</span><span class="sxs-lookup"><span data-stu-id="76498-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="76498-117">Это может произойти, если среда выполнения должна ждать, пока он достигает безопасной точки для вызова MDA, вместо вызова MDA при ее обнаружении.</span><span class="sxs-lookup"><span data-stu-id="76498-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="76498-118">Это также означает, что среда выполнения может возникнуть ряд Помощники отладки управляемого кода в один набор в очередь обратных вызовов (аналогично операции «присоединение» событий).</span><span class="sxs-lookup"><span data-stu-id="76498-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="76498-119">Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить CLR позволяет очистить память, занятая MDA.</span><span class="sxs-lookup"><span data-stu-id="76498-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="76498-120">Освобождение экземпляра может повысить производительность, если нескольких MDA.</span><span class="sxs-lookup"><span data-stu-id="76498-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76498-121">Требования</span><span class="sxs-lookup"><span data-stu-id="76498-121">Requirements</span></span>  
 <span data-ttu-id="76498-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76498-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76498-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76498-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76498-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76498-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="76498-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="76498-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="76498-126">См. также</span><span class="sxs-lookup"><span data-stu-id="76498-126">See also</span></span>

- [<span data-ttu-id="76498-127">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="76498-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="76498-128">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="76498-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="76498-129">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="76498-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
