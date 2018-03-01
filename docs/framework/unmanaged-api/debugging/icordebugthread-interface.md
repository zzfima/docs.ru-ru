---
title: "ICorDebugThread интерфейс1"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="36ae0-102">ICorDebugThread интерфейс1</span><span class="sxs-lookup"><span data-stu-id="36ae0-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="36ae0-103">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="36ae0-103">Represents a thread in a process.</span></span> <span data-ttu-id="36ae0-104">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="36ae0-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36ae0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="36ae0-105">Methods</span></span>  
  
|<span data-ttu-id="36ae0-106">Метод</span><span class="sxs-lookup"><span data-stu-id="36ae0-106">Method</span></span>|<span data-ttu-id="36ae0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="36ae0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36ae0-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="36ae0-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="36ae0-109">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="36ae0-109">This method is not implemented.</span></span> <span data-ttu-id="36ae0-110">Не используйте его.</span><span class="sxs-lookup"><span data-stu-id="36ae0-110">Do not use it.</span></span>|  
|[<span data-ttu-id="36ae0-111">Метод CreateEval</span><span class="sxs-lookup"><span data-stu-id="36ae0-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="36ae0-112">Создает объект ICorDebugEval, который работает в данном `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-113">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="36ae0-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="36ae0-114">Создает объект ICorDebugStepper, который позволяет проходить через активного кадра, в этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-115">Метод EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="36ae0-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="36ae0-116">Получает указатель интерфейса на перечислитель ICorDebugChainEnum, содержащий всех цепочек стека в этом `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-117">Метод GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="36ae0-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="36ae0-118">Возвращает указатель на интерфейс для активного ICorDebugChain в данном `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-119">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="36ae0-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="36ae0-120">Возвращает указатель на интерфейс для активного ICorDebugFrame в данном `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-121">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="36ae0-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="36ae0-122">Возвращает указатель на интерфейс в домен приложения, в котором `ICorDebugThread` в данный момент.</span><span class="sxs-lookup"><span data-stu-id="36ae0-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="36ae0-123">Метод GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="36ae0-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="36ae0-124">Получает указатель интерфейса на объект ICorDebugValue, представляющий исключение в настоящее время в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="36ae0-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="36ae0-125">Метод GetDebugState</span><span class="sxs-lookup"><span data-stu-id="36ae0-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="36ae0-126">Возвращает значение CorDebugThreadState, описывающее текущее состояние отладки данного `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-127">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="36ae0-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="36ae0-128">Возвращает текущий дескриптор для активной части это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-129">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="36ae0-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="36ae0-130">Возвращает идентификатор текущей операционной системы активной части это `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-131">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="36ae0-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="36ae0-132">Возвращает указатель на интерфейс среды выполнения (CLR) потоку выполнения.</span><span class="sxs-lookup"><span data-stu-id="36ae0-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="36ae0-133">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="36ae0-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="36ae0-134">Возвращает указатель интерфейса, для которого данный процесс `ICorDebugThread` эти формы.</span><span class="sxs-lookup"><span data-stu-id="36ae0-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="36ae0-135">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="36ae0-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="36ae0-136">Получает указатель интерфейса на набор регистров, связанных с этим `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-137">Метод GetUserState</span><span class="sxs-lookup"><span data-stu-id="36ae0-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="36ae0-138">Возвращает поразрядное сочетание значений CorDebugUserState, описывающих текущее состояние данного объекта `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="36ae0-139">Метод SetDebugState</span><span class="sxs-lookup"><span data-stu-id="36ae0-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="36ae0-140">Задает побитовое сочетание `CorDebugThreadState` значения, описывающие состояние отладки данного `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="36ae0-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36ae0-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="36ae0-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36ae0-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="36ae0-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ae0-143">Требования</span><span class="sxs-lookup"><span data-stu-id="36ae0-143">Requirements</span></span>  
 <span data-ttu-id="36ae0-144">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36ae0-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ae0-145">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36ae0-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36ae0-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36ae0-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36ae0-147">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ae0-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ae0-148">См. также</span><span class="sxs-lookup"><span data-stu-id="36ae0-148">See Also</span></span>  
 [<span data-ttu-id="36ae0-149">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="36ae0-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
