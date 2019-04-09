---
title: Интерфейс ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184708"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="7d934-102">Интерфейс ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="7d934-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="7d934-103">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="7d934-103">Represents a thread in a process.</span></span> <span data-ttu-id="7d934-104">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="7d934-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d934-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7d934-105">Methods</span></span>  
  
|<span data-ttu-id="7d934-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7d934-106">Method</span></span>|<span data-ttu-id="7d934-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7d934-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d934-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="7d934-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="7d934-109">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="7d934-109">This method is not implemented.</span></span> <span data-ttu-id="7d934-110">Не используйте его.</span><span class="sxs-lookup"><span data-stu-id="7d934-110">Do not use it.</span></span>|  
|[<span data-ttu-id="7d934-111">Метод CreateEval</span><span class="sxs-lookup"><span data-stu-id="7d934-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="7d934-112">Создает объект ICorDebugEval, который работает на этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-113">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="7d934-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="7d934-114">Создает объект ICorDebugStepper, который позволяет пошаговое выполнение активного кадра в этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-115">Метод EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="7d934-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="7d934-116">Получает указатель интерфейса на перечислитель ICorDebugChainEnum, содержащий всех цепочек стека в этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-117">Метод GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="7d934-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="7d934-118">Получает указатель интерфейса на active ICorDebugChain об этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-119">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="7d934-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="7d934-120">Получает указатель интерфейса на active ICorDebugFrame об этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-121">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="7d934-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="7d934-122">Получает указатель интерфейса на домен приложения, в котором этот `ICorDebugThread` в данный момент.</span><span class="sxs-lookup"><span data-stu-id="7d934-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="7d934-123">Метод GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="7d934-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="7d934-124">Получает указатель на интерфейс ICorDebugValue объект, представляющий исключение в настоящее время в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="7d934-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="7d934-125">Метод GetDebugState</span><span class="sxs-lookup"><span data-stu-id="7d934-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="7d934-126">Возвращает значение CorDebugThreadState, описывающее текущее состояние отладки это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-127">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="7d934-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="7d934-128">Получает текущий дескриптор для активной части это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-129">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="7d934-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="7d934-130">Возвращает идентификатор текущей операционной системы, активной части это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-131">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="7d934-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="7d934-132">Получает указатель интерфейса среды выполнения (CLR) потоку выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d934-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="7d934-133">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="7d934-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="7d934-134">Получает указатель интерфейса, для которого данный процесс `ICorDebugThread` формы.</span><span class="sxs-lookup"><span data-stu-id="7d934-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="7d934-135">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="7d934-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="7d934-136">Получает указатель интерфейса на набор регистров, связанных с этим `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-137">Метод GetUserState</span><span class="sxs-lookup"><span data-stu-id="7d934-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="7d934-138">Возвращает побитовое сочетание CorDebugUserState значения, описывающие текущее состояние данного объекта `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d934-139">Метод SetDebugState</span><span class="sxs-lookup"><span data-stu-id="7d934-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="7d934-140">Задает побитовое сочетание `CorDebugThreadState` значения, описывающие состояние отладки это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d934-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d934-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d934-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d934-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7d934-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d934-143">Требования</span><span class="sxs-lookup"><span data-stu-id="7d934-143">Requirements</span></span>  
 <span data-ttu-id="7d934-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d934-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d934-145">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d934-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d934-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d934-146">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7d934-147">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7d934-147">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d934-148">См. также</span><span class="sxs-lookup"><span data-stu-id="7d934-148">See also</span></span>

- [<span data-ttu-id="7d934-149">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7d934-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
