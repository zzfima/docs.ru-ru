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
ms.openlocfilehash: c8c6b40f7a9c63a577140209eed65436040addcb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125377"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="1d9c9-102">Метод ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="1d9c9-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="1d9c9-103">Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d9c9-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d9c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d9c9-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="1d9c9-106">Не используется.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d9c9-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="1d9c9-107">Remarks</span></span>  
 <span data-ttu-id="1d9c9-108">`Stop` выполняет совместную работу во всех потоках, выполняющих управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="1d9c9-109">Во время сеанса отладки, доступного только для управляемого кода, неуправляемые потоки могут продолжать выполняться (но будут заблокированы при попытке вызвать управляемый код).</span><span class="sxs-lookup"><span data-stu-id="1d9c9-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="1d9c9-110">Во время сеанса отладки взаимодействия неуправляемые потоки также будут остановлены.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="1d9c9-111">Значение `dwTimeoutIgnored` в настоящее время игнорируется и обрабатывается как бесконечное (-1).</span><span class="sxs-lookup"><span data-stu-id="1d9c9-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="1d9c9-112">Если совместная остановка завершается сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d9c9-113">единственным синхронным методом в API отладки является `Stop`.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="1d9c9-114">Если `Stop` возвращает значение S_OK, процесс останавливается.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="1d9c9-115">Обратный вызов не предоставляется для уведомления прослушивателей об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="1d9c9-116">Отладчик должен вызвать [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , чтобы разрешить возобновление процесса.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="1d9c9-117">Отладчик поддерживает счетчик "останавливается".</span><span class="sxs-lookup"><span data-stu-id="1d9c9-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="1d9c9-118">Когда счетчик переходит в нулевое значение, контроллер возобновляется.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="1d9c9-119">Каждый вызов `Stop` или каждый отправленный обратный вызов увеличивает счетчик.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="1d9c9-120">Каждый вызов `ICorDebugController::Continue` уменьшает счетчик.</span><span class="sxs-lookup"><span data-stu-id="1d9c9-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9c9-121">Требования</span><span class="sxs-lookup"><span data-stu-id="1d9c9-121">Requirements</span></span>  
 <span data-ttu-id="1d9c9-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d9c9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9c9-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d9c9-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d9c9-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d9c9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d9c9-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9c9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9c9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1d9c9-126">See also</span></span>
