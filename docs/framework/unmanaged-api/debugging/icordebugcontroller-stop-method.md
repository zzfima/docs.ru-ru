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
ms.openlocfilehash: 83bb52f7f2035605914e2fe72ce2daf78de5bc1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749905"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="8f891-102">Метод ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="8f891-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="8f891-103">Выполняет совместную остановку во всех потоках, работающих под управлением управляемого кода в процессе.</span><span class="sxs-lookup"><span data-stu-id="8f891-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f891-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f891-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f891-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f891-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="8f891-106">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8f891-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f891-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f891-107">Remarks</span></span>  
 <span data-ttu-id="8f891-108">`Stop` выполняет согласованную остановку всех потоков, выполняющих управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="8f891-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="8f891-109">Во время сеанса отладки только управляемого, неуправляемые потоки может продолжить свое выполнение (но будет блокироваться при попытке вызвать управляемый код).</span><span class="sxs-lookup"><span data-stu-id="8f891-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="8f891-110">Во время сеанса отладки взаимодействия неуправляемые потоки также останавливается.</span><span class="sxs-lookup"><span data-stu-id="8f891-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="8f891-111">`dwTimeoutIgnored` Значение в настоящее время игнорируется и обрабатывается как бесконечность (– 1).</span><span class="sxs-lookup"><span data-stu-id="8f891-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="8f891-112">Если согласованная остановка завершилась сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается значение E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="8f891-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f891-113">`Stop` является единственным методом синхронизации в API отладки.</span><span class="sxs-lookup"><span data-stu-id="8f891-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="8f891-114">Когда `Stop` возвращает S_OK, процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="8f891-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="8f891-115">Обратный вызов не предоставляется для уведомления прослушивателей об остановке.</span><span class="sxs-lookup"><span data-stu-id="8f891-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="8f891-116">Отладчик должен вызвать [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) позволяет возобновить процесс.</span><span class="sxs-lookup"><span data-stu-id="8f891-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="8f891-117">Отладчик поддерживает счетчик stop.</span><span class="sxs-lookup"><span data-stu-id="8f891-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="8f891-118">Когда счетчик становится равным нулю, возобновляется контроллера.</span><span class="sxs-lookup"><span data-stu-id="8f891-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="8f891-119">Каждый вызов `Stop` или каждой отправляемой обратного вызова, увеличивает значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="8f891-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="8f891-120">Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="8f891-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f891-121">Требования</span><span class="sxs-lookup"><span data-stu-id="8f891-121">Requirements</span></span>  
 <span data-ttu-id="8f891-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f891-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f891-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f891-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f891-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f891-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f891-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f891-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f891-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8f891-126">See also</span></span>
