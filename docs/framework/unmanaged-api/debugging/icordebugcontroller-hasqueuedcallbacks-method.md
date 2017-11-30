---
title: "Метод ICorDebugController::HasQueuedCallbacks"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81830cbadcf9fb359b8e1a74cd47f9d18543c29c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="a599d-102">Метод ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="a599d-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="a599d-103">Возвращает значение, указывающее ли любого управляемого обратных вызовов в настоящее время в очереди для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="a599d-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a599d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a599d-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a599d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a599d-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="a599d-106">[in] Указатель на объект «ICorDebugThread», представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="a599d-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="a599d-107">[out] Указатель на значение, являющееся `true` Если любой управляемый обратных вызовов в настоящий момент в очереди для указанного потока, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="a599d-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a599d-108">Если указано значение null для `pThread` параметр `HasQueuedCallbacks` вернет `true` Если в настоящий момент в очереди управляемого обратные вызовы для любого потока.</span><span class="sxs-lookup"><span data-stu-id="a599d-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a599d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a599d-109">Remarks</span></span>  
 <span data-ttu-id="a599d-110">Обратные вызовы будет отправлено по одному, каждый раз [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="a599d-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="a599d-111">Отладчик может установить этот флаг, если ему нужно сообщить нескольких событиях отладки, которые произошли одновременно.</span><span class="sxs-lookup"><span data-stu-id="a599d-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="a599d-112">Постановке в очередь событий отладки, они уже произошли, поэтому отладчик должен обработать всю очередь, чтобы штата отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="a599d-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="a599d-113">(Вызов `ICorDebugController::Continue` истощения очереди.) Например, если очередь содержит два события отладки потока *X*, и отладчик приостанавливает выполнение потока *X* после первого события отладки, а затем вызывает `ICorDebugController::Continue`, второе событие отладки для поток *X* будет отправлено, несмотря на то, что этот поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="a599d-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a599d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a599d-114">Requirements</span></span>  
 <span data-ttu-id="a599d-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a599d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a599d-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a599d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a599d-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a599d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a599d-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a599d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a599d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a599d-119">See Also</span></span>  
 
