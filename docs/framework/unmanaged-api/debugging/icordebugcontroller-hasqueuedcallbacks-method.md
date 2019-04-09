---
title: Метод ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce6ad24e5e670db21d3a6942ab4650a68ae44568
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102704"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="5cefe-102">Метод ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="5cefe-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="5cefe-103">Получает значение, указывающее ли любой управляемый оно для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="5cefe-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cefe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cefe-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cefe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cefe-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="5cefe-106">[in] Указатель на объект «ICorDebugThread», представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="5cefe-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="5cefe-107">[out] Указатель на значение, являющееся `true` в случае любого управляемого обратные вызовы в настоящее время в очереди для указанного потока, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="5cefe-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="5cefe-108">Если указано значение null для `pThread` параметра `HasQueuedCallbacks` вернет `true` Если в настоящий момент управляемый обратные вызовы в очередь для любого потока.</span><span class="sxs-lookup"><span data-stu-id="5cefe-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cefe-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cefe-109">Remarks</span></span>  
 <span data-ttu-id="5cefe-110">Обратные вызовы будут отправляемой поочередно, каждый раз [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="5cefe-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="5cefe-111">Отладчик может установить этот флаг, если он хочет получить отчет несколько отладочных событий, которые выполняются одновременно.</span><span class="sxs-lookup"><span data-stu-id="5cefe-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="5cefe-112">При отладке события находятся в очереди, они уже произошли, поэтому отладчик должен обработать всю очередь, чтобы о состоянии отлаживаемой программы.</span><span class="sxs-lookup"><span data-stu-id="5cefe-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="5cefe-113">(Вызов `ICorDebugController::Continue` для очистки очереди.) Например, если очередь содержит два события отладки потока *X*, и отладчик приостанавливает поток *X* после первого события отладки, а затем вызывает `ICorDebugController::Continue`, второе событие отладки для поток *X* несмотря на то, что поток был приостановлен, будут переданы.</span><span class="sxs-lookup"><span data-stu-id="5cefe-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cefe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5cefe-114">Requirements</span></span>  
 <span data-ttu-id="5cefe-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cefe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cefe-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cefe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cefe-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cefe-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5cefe-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5cefe-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cefe-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5cefe-119">See also</span></span>
