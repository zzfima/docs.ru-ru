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
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411614"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="931b3-102">Метод ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="931b3-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="931b3-103">Возвращает значение, указывающее ли любого управляемого обратных вызовов в настоящее время в очереди для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="931b3-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="931b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="931b3-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="931b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="931b3-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="931b3-106">[in] Указатель на объект «ICorDebugThread», представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="931b3-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="931b3-107">[out] Указатель на значение, являющееся `true` Если любой управляемый обратных вызовов в настоящий момент в очереди для указанного потока, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="931b3-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="931b3-108">Если указано значение null для `pThread` параметр `HasQueuedCallbacks` вернет `true` Если в настоящий момент в очереди управляемого обратные вызовы для любого потока.</span><span class="sxs-lookup"><span data-stu-id="931b3-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="931b3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="931b3-109">Remarks</span></span>  
 <span data-ttu-id="931b3-110">Обратные вызовы будет отправлено по одному, каждый раз [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="931b3-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="931b3-111">Отладчик может установить этот флаг, если ему нужно сообщить нескольких событиях отладки, которые произошли одновременно.</span><span class="sxs-lookup"><span data-stu-id="931b3-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="931b3-112">Постановке в очередь событий отладки, они уже произошли, поэтому отладчик должен обработать всю очередь, чтобы штата отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="931b3-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="931b3-113">(Вызов `ICorDebugController::Continue` истощения очереди.) Например, если очередь содержит два события отладки потока *X*, и отладчик приостанавливает выполнение потока *X* после первого события отладки, а затем вызывает `ICorDebugController::Continue`, второе событие отладки для поток *X* будет отправлено, несмотря на то, что этот поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="931b3-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="931b3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="931b3-114">Requirements</span></span>  
 <span data-ttu-id="931b3-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="931b3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="931b3-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="931b3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="931b3-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="931b3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="931b3-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="931b3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931b3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="931b3-119">See Also</span></span>  
 
