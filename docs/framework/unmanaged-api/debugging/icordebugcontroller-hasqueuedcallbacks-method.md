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
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125397"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="ad3d1-102">Метод ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="ad3d1-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="ad3d1-103">Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad3d1-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad3d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad3d1-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="ad3d1-106">окне Указатель на объект "ICorDebugThread", представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="ad3d1-107">заполняет Указатель на значение, которое `true`, если в настоящий момент в очереди для указанного потока находятся управляемые обратные вызовы. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="ad3d1-108">Если для параметра `pThread` указано значение null, `HasQueuedCallbacks` будет возвращать `true`, если в настоящий момент в очереди есть управляемые обратные вызовы для любого потока.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad3d1-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="ad3d1-109">Remarks</span></span>  
 <span data-ttu-id="ad3d1-110">Обратные вызовы будут отправлены по одному, каждый раз, когда вызывается [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ad3d1-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="ad3d1-111">Отладчик может проверить этот флаг, если он хочет сообщить о нескольких событиях отладки, происходящих одновременно.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="ad3d1-112">Когда события отладки помещаются в очередь, они уже были выполнены, поэтому отладчик должен очистить всю очередь, чтобы убедиться в состоянии отлаживаемой программы.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="ad3d1-113">(Вызовите `ICorDebugController::Continue` для очистки очереди.) Например, если очередь содержит два события отладки в потоке *x*, а отладчик приостанавливает поток *x* после первого события отладки и затем вызывает `ICorDebugController::Continue`, второе событие отладки для потока *X* будет отправлено, хотя поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad3d1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ad3d1-114">Requirements</span></span>  
 <span data-ttu-id="ad3d1-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad3d1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad3d1-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad3d1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad3d1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad3d1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad3d1-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad3d1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3d1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3d1-119">See also</span></span>
