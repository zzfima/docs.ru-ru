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
ms.openlocfilehash: 64b09c173e2f66d4c650083cc12f8a0ac2c92007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417232"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="6d636-102">Метод ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="6d636-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="6d636-103">Предоставляет уведомление о том, что выполнение кода обнаружил помощник по отладке управляемого (кода MDA) в отлаживаемом приложении.</span><span class="sxs-lookup"><span data-stu-id="6d636-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d636-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d636-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d636-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d636-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="6d636-106">[in] Указатель на интерфейс ICorDebugController, предоставляющую процесс или домен приложения, в котором произошло MDA.</span><span class="sxs-lookup"><span data-stu-id="6d636-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="6d636-107">Отладчик не следует делать никаких предположений о типе контроллера: процесс или домен приложения, несмотря на то, что он всегда может запросить выполнение такого определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6d636-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6d636-108">[in] Указатель на интерфейс ICorDebugThread, который представляет управляемый поток, в котором произошло событие отладки.</span><span class="sxs-lookup"><span data-stu-id="6d636-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="6d636-109">Если MDA встречается на неуправляемый поток, значение `pThread` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="6d636-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="6d636-110">Из самого объекта MDA, необходимо получить идентификатор потока операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="6d636-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="6d636-111">[in] Указатель на [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) интерфейс, который предоставляет сведения об MDA.</span><span class="sxs-lookup"><span data-stu-id="6d636-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d636-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d636-112">Remarks</span></span>  
 <span data-ttu-id="6d636-113">MDA — это эвристическое предупреждение и не требуют никакого отладчика явного действия, за исключением вызова [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="6d636-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="6d636-114">Общеязыковая среда выполнения (CLR) можно определить MDA, и какие данные оказываются в любой данный MDA в любой момент.</span><span class="sxs-lookup"><span data-stu-id="6d636-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="6d636-115">Таким образом отладчики не должны использовать все функции, требующие определенных шаблонов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="6d636-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="6d636-116">Помощники отладки управляемого кода может быть в очередь и вызывать сразу же после обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6d636-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="6d636-117">Это может произойти, если среда выполнения должна ожидать, пока не достигнет безопасной точки для вызова управляемого кода, вместо вызова MDA при его обнаружении.</span><span class="sxs-lookup"><span data-stu-id="6d636-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="6d636-118">Это также означает, что среда выполнения может вызвать несколько помощников в один набор в очередь обратных вызовов (аналогично операции события «присоединить»).</span><span class="sxs-lookup"><span data-stu-id="6d636-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="6d636-119">Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить CLR повторно использовать память, занятая MDA.</span><span class="sxs-lookup"><span data-stu-id="6d636-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="6d636-120">Освобождение экземпляра может повысить производительность, если нескольких MDA.</span><span class="sxs-lookup"><span data-stu-id="6d636-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d636-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6d636-121">Requirements</span></span>  
 <span data-ttu-id="6d636-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d636-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d636-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d636-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d636-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d636-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d636-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d636-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d636-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6d636-126">See Also</span></span>  
 [<span data-ttu-id="6d636-127">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="6d636-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="6d636-128">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="6d636-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="6d636-129">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6d636-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
