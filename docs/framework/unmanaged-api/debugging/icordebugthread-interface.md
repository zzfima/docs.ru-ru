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
ms.openlocfilehash: 1517d686c50923f5599e33436e0ad6126e8be140
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923145"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="9c203-102">Интерфейс ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="9c203-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="9c203-103">Представляет поток в процессе.</span><span class="sxs-lookup"><span data-stu-id="9c203-103">Represents a thread in a process.</span></span> <span data-ttu-id="9c203-104">Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="9c203-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c203-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9c203-105">Methods</span></span>  
  
|<span data-ttu-id="9c203-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9c203-106">Method</span></span>|<span data-ttu-id="9c203-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9c203-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c203-108">Метод ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="9c203-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="9c203-109">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="9c203-109">This method is not implemented.</span></span> <span data-ttu-id="9c203-110">Не используйте его.</span><span class="sxs-lookup"><span data-stu-id="9c203-110">Do not use it.</span></span>|  
|[<span data-ttu-id="9c203-111">Метод CreateEval</span><span class="sxs-lookup"><span data-stu-id="9c203-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="9c203-112">Создает объект ICorDebugEval, который работает с этим `ICorDebugThread`объектом.</span><span class="sxs-lookup"><span data-stu-id="9c203-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-113">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="9c203-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="9c203-114">Создает объект ICorDebugStepper, позволяющий пошаговое выполнение активного кадра в этом `ICorDebugThread`объекте.</span><span class="sxs-lookup"><span data-stu-id="9c203-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-115">Метод EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="9c203-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="9c203-116">Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в `ICorDebugThread`этом.</span><span class="sxs-lookup"><span data-stu-id="9c203-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-117">Метод GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="9c203-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="9c203-118">Возвращает указатель интерфейса на активный ICorDebugChain для этого `ICorDebugThread`объекта.</span><span class="sxs-lookup"><span data-stu-id="9c203-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-119">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="9c203-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="9c203-120">Получает указатель интерфейса на активный объект ICorDebugFrame для этого `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="9c203-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-121">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="9c203-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="9c203-122">Возвращает указатель интерфейса на домен приложения, в котором `ICorDebugThread` выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="9c203-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="9c203-123">Метод GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="9c203-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="9c203-124">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="9c203-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="9c203-125">Метод GetDebugState</span><span class="sxs-lookup"><span data-stu-id="9c203-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="9c203-126">Возвращает значение Кордебугсреадстате, описывающее текущее состояние отладки этого `ICorDebugThread`объекта.</span><span class="sxs-lookup"><span data-stu-id="9c203-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-127">Метод GetHandle</span><span class="sxs-lookup"><span data-stu-id="9c203-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="9c203-128">Возвращает текущий обработчик для активной части этого `ICorDebugThread`объекта.</span><span class="sxs-lookup"><span data-stu-id="9c203-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-129">Метод GetID</span><span class="sxs-lookup"><span data-stu-id="9c203-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="9c203-130">Возвращает идентификатор текущей операционной системы активной части `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="9c203-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-131">Метод GetObject</span><span class="sxs-lookup"><span data-stu-id="9c203-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="9c203-132">Возвращает указатель интерфейса на поток среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9c203-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="9c203-133">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="9c203-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="9c203-134">Возвращает указатель интерфейса для процесса, частью которого является эта `ICorDebugThread` форма.</span><span class="sxs-lookup"><span data-stu-id="9c203-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="9c203-135">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="9c203-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="9c203-136">Возвращает указатель интерфейса на набор регистров, связанный с этим `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="9c203-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-137">Метод GetUserState</span><span class="sxs-lookup"><span data-stu-id="9c203-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="9c203-138">Возвращает побитовое сочетание значений Кордебугусерстате, описывающих текущее состояние этого `ICorDebugThread`объекта.</span><span class="sxs-lookup"><span data-stu-id="9c203-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="9c203-139">Метод SetDebugState</span><span class="sxs-lookup"><span data-stu-id="9c203-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="9c203-140">Задает побитовое сочетание `CorDebugThreadState` значений, описывающих состояние отладки этого `ICorDebugThread`объекта.</span><span class="sxs-lookup"><span data-stu-id="9c203-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c203-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c203-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c203-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9c203-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c203-143">Требования</span><span class="sxs-lookup"><span data-stu-id="9c203-143">Requirements</span></span>  
 <span data-ttu-id="9c203-144">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c203-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c203-145">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9c203-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c203-146">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="9c203-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c203-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c203-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c203-148">См. также</span><span class="sxs-lookup"><span data-stu-id="9c203-148">See also</span></span>

- [<span data-ttu-id="9c203-149">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9c203-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
