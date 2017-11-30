---
title: "ICorDebugChain интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain
helpviewer_keywords: ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f964b5390e601b518acad44dd6fd170399ff0af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="4ab71-102">ICorDebugChain интерфейс1</span><span class="sxs-lookup"><span data-stu-id="4ab71-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="4ab71-103">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="4ab71-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ab71-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4ab71-104">Methods</span></span>  
  
|<span data-ttu-id="4ab71-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4ab71-105">Method</span></span>|<span data-ttu-id="4ab71-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4ab71-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ab71-107">Метод EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="4ab71-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="4ab71-108">Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="4ab71-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="4ab71-109">Getactiveframe-метод</span><span class="sxs-lookup"><span data-stu-id="4ab71-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="4ab71-110">Получает активный (то есть последней) кадра в цепочке.</span><span class="sxs-lookup"><span data-stu-id="4ab71-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="4ab71-111">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="4ab71-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="4ab71-112">Получает цепь, вызванной этой цепи.</span><span class="sxs-lookup"><span data-stu-id="4ab71-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="4ab71-113">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="4ab71-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="4ab71-114">Получает цепь, вызвавшую данную цепь.</span><span class="sxs-lookup"><span data-stu-id="4ab71-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="4ab71-115">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="4ab71-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="4ab71-116">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="4ab71-116">Not implemented.</span></span>|  
|[<span data-ttu-id="4ab71-117">GetNext-метод</span><span class="sxs-lookup"><span data-stu-id="4ab71-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="4ab71-118">Получает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="4ab71-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="4ab71-119">Метод GetPrevious</span><span class="sxs-lookup"><span data-stu-id="4ab71-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="4ab71-120">Возвращает предыдущую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="4ab71-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="4ab71-121">Метод GetReason</span><span class="sxs-lookup"><span data-stu-id="4ab71-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="4ab71-122">Возвращает причину происхождения данной вызывающей цепи.</span><span class="sxs-lookup"><span data-stu-id="4ab71-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="4ab71-123">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="4ab71-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="4ab71-124">Получает набор регистров для активной части этой цепи.</span><span class="sxs-lookup"><span data-stu-id="4ab71-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="4ab71-125">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="4ab71-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="4ab71-126">Возвращает диапазон адресов сегмента стека для этой цепи.</span><span class="sxs-lookup"><span data-stu-id="4ab71-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="4ab71-127">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="4ab71-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="4ab71-128">Получает часть физическом потоке, — это цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="4ab71-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="4ab71-129">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="4ab71-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="4ab71-130">Возвращает значение, указывающее, выполняется ли эта цепочка управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="4ab71-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ab71-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ab71-131">Remarks</span></span>  
 <span data-ttu-id="4ab71-132">Кадры стека в цепи занимают непрерывное пространство стека и используют один поток и контекст.</span><span class="sxs-lookup"><span data-stu-id="4ab71-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="4ab71-133">Цепь может представлять любой цепочки управляемого или неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="4ab71-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="4ab71-134">Пустой `ICorDebugChain` экземпляр представляет неуправляемую цепь.</span><span class="sxs-lookup"><span data-stu-id="4ab71-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ab71-135">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4ab71-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab71-136">Требования</span><span class="sxs-lookup"><span data-stu-id="4ab71-136">Requirements</span></span>  
 <span data-ttu-id="4ab71-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ab71-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab71-138">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ab71-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ab71-139">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ab71-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ab71-140">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab71-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab71-141">См. также</span><span class="sxs-lookup"><span data-stu-id="4ab71-141">See Also</span></span>  
 [<span data-ttu-id="4ab71-142">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4ab71-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
