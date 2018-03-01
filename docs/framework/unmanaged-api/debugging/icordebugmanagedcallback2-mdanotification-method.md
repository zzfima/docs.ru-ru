---
title: "Метод ICorDebugManagedCallback2::MDANotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a58e286feb3387557d0a37c463f2af67abf8cc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="90ffd-102">Метод ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="90ffd-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="90ffd-103">Предоставляет уведомление о том, что выполнение кода обнаружил помощник по отладке управляемого (кода MDA) в отлаживаемом приложении.</span><span class="sxs-lookup"><span data-stu-id="90ffd-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ffd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90ffd-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90ffd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90ffd-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="90ffd-106">[in] Указатель на интерфейс ICorDebugController, предоставляющую процесс или домен приложения, в котором произошло MDA.</span><span class="sxs-lookup"><span data-stu-id="90ffd-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="90ffd-107">Отладчик не следует делать никаких предположений о типе контроллера: процесс или домен приложения, несмотря на то, что он всегда может запросить выполнение такого определения интерфейса.</span><span class="sxs-lookup"><span data-stu-id="90ffd-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="90ffd-108">[in] Указатель на интерфейс ICorDebugThread, который представляет управляемый поток, в котором произошло событие отладки.</span><span class="sxs-lookup"><span data-stu-id="90ffd-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="90ffd-109">Если MDA встречается на неуправляемый поток, значение `pThread` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="90ffd-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="90ffd-110">Из самого объекта MDA, необходимо получить идентификатор потока операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="90ffd-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="90ffd-111">[in] Указатель на [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) интерфейс, который предоставляет сведения об MDA.</span><span class="sxs-lookup"><span data-stu-id="90ffd-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90ffd-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="90ffd-112">Remarks</span></span>  
 <span data-ttu-id="90ffd-113">MDA — это эвристическое предупреждение и не требуют никакого отладчика явного действия, за исключением вызова [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="90ffd-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="90ffd-114">Общеязыковая среда выполнения (CLR) можно определить MDA, и какие данные оказываются в любой данный MDA в любой момент.</span><span class="sxs-lookup"><span data-stu-id="90ffd-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="90ffd-115">Таким образом отладчики не должны использовать все функции, требующие определенных шаблонов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="90ffd-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="90ffd-116">Помощники отладки управляемого кода может быть в очередь и вызывать сразу же после обнаружения.</span><span class="sxs-lookup"><span data-stu-id="90ffd-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="90ffd-117">Это может произойти, если среда выполнения должна ожидать, пока не достигнет безопасной точки для вызова управляемого кода, вместо вызова MDA при его обнаружении.</span><span class="sxs-lookup"><span data-stu-id="90ffd-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="90ffd-118">Это также означает, что среда выполнения может вызвать несколько помощников в один набор в очередь обратных вызовов (аналогично операции события «присоединить»).</span><span class="sxs-lookup"><span data-stu-id="90ffd-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="90ffd-119">Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить CLR повторно использовать память, занятая MDA.</span><span class="sxs-lookup"><span data-stu-id="90ffd-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="90ffd-120">Освобождение экземпляра может повысить производительность, если нескольких MDA.</span><span class="sxs-lookup"><span data-stu-id="90ffd-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ffd-121">Требования</span><span class="sxs-lookup"><span data-stu-id="90ffd-121">Requirements</span></span>  
 <span data-ttu-id="90ffd-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90ffd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90ffd-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90ffd-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90ffd-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90ffd-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90ffd-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90ffd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ffd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="90ffd-126">See Also</span></span>  
 [<span data-ttu-id="90ffd-127">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="90ffd-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="90ffd-128">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="90ffd-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="90ffd-129">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="90ffd-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
