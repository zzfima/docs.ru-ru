---
title: Метод ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cb5b091aadbdd503dd7988f713f40a00876a2dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608330"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="16252-102">Метод ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="16252-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="16252-103">Выполняет совместную остановку во всех потоках, работающих под управлением управляемого кода в процессе.</span><span class="sxs-lookup"><span data-stu-id="16252-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16252-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16252-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16252-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16252-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="16252-106">Не используется.</span><span class="sxs-lookup"><span data-stu-id="16252-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16252-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="16252-107">Remarks</span></span>  
 <span data-ttu-id="16252-108">`Stop` выполняет согласованную остановку всех потоков, выполняющих управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="16252-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="16252-109">Во время сеанса отладки только управляемого, неуправляемые потоки может продолжить свое выполнение (но будет блокироваться при попытке вызвать управляемый код).</span><span class="sxs-lookup"><span data-stu-id="16252-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="16252-110">Во время сеанса отладки взаимодействия неуправляемые потоки также останавливается.</span><span class="sxs-lookup"><span data-stu-id="16252-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="16252-111">`dwTimeoutIgnored` Значение в настоящее время игнорируется и обрабатывается как бесконечность (– 1).</span><span class="sxs-lookup"><span data-stu-id="16252-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="16252-112">Если согласованная остановка завершилась сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается значение E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="16252-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16252-113">`Stop` является единственным методом синхронизации в API отладки.</span><span class="sxs-lookup"><span data-stu-id="16252-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="16252-114">Когда `Stop` возвращает S_OK, процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="16252-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="16252-115">Обратный вызов не предоставляется для уведомления прослушивателей об остановке.</span><span class="sxs-lookup"><span data-stu-id="16252-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="16252-116">Отладчик должен вызвать [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) позволяет возобновить процесс.</span><span class="sxs-lookup"><span data-stu-id="16252-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="16252-117">Отладчик поддерживает счетчик stop.</span><span class="sxs-lookup"><span data-stu-id="16252-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="16252-118">Когда счетчик становится равным нулю, возобновляется контроллера.</span><span class="sxs-lookup"><span data-stu-id="16252-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="16252-119">Каждый вызов `Stop` или каждой отправляемой обратного вызова, увеличивает значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="16252-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="16252-120">Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="16252-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16252-121">Требования</span><span class="sxs-lookup"><span data-stu-id="16252-121">Requirements</span></span>  
 <span data-ttu-id="16252-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16252-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16252-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16252-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16252-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16252-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16252-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16252-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16252-126">См. также</span><span class="sxs-lookup"><span data-stu-id="16252-126">See also</span></span>

