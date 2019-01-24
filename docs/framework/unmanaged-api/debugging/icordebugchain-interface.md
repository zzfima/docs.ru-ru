---
title: Интерфейс1 ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bb716f1ad4087642a76dc84266ec6d3f46c1ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571208"
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="ef919-102">Интерфейс1 ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="ef919-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="ef919-103">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="ef919-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef919-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ef919-104">Methods</span></span>  
  
|<span data-ttu-id="ef919-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ef919-105">Method</span></span>|<span data-ttu-id="ef919-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ef919-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef919-107">Метод EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="ef919-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="ef919-108">Возвращает перечислитель, содержащий все управляемые фреймы стека в цепочке, начиная с последнего.</span><span class="sxs-lookup"><span data-stu-id="ef919-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="ef919-109">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="ef919-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="ef919-110">Получает активный (то есть самой последней) кадра в цепочке.</span><span class="sxs-lookup"><span data-stu-id="ef919-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="ef919-111">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="ef919-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="ef919-112">Получает цепочку, вызванная этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="ef919-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="ef919-113">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="ef919-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="ef919-114">Получает цепочку, вызвавшей эту цепочку.</span><span class="sxs-lookup"><span data-stu-id="ef919-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="ef919-115">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="ef919-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="ef919-116">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="ef919-116">Not implemented.</span></span>|  
|[<span data-ttu-id="ef919-117">Метод GetNext</span><span class="sxs-lookup"><span data-stu-id="ef919-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="ef919-118">Получает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="ef919-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="ef919-119">Метод GetPrevious</span><span class="sxs-lookup"><span data-stu-id="ef919-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="ef919-120">Получает предыдущий цепочки кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="ef919-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="ef919-121">Метод GetReason</span><span class="sxs-lookup"><span data-stu-id="ef919-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="ef919-122">Получает причину происхождения этой цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="ef919-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="ef919-123">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ef919-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="ef919-124">Получает набор регистров для активной части этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="ef919-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="ef919-125">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="ef919-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="ef919-126">Получает диапазон адресов сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="ef919-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="ef919-127">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="ef919-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="ef919-128">Получает часть физических обсуждение, на которое эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="ef919-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="ef919-129">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="ef919-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="ef919-130">Получает значение, указывающее, выполняется ли эта цепочка управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ef919-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef919-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef919-131">Remarks</span></span>  
 <span data-ttu-id="ef919-132">Кадры стека в цепочке занимают непрерывное пространство стека и используют один поток и контекст.</span><span class="sxs-lookup"><span data-stu-id="ef919-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="ef919-133">Цепь может представлять любой цепочки управляемого или неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ef919-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="ef919-134">Пустой `ICorDebugChain` экземпляр представляет созданию цепочки неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ef919-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef919-135">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ef919-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef919-136">Требования</span><span class="sxs-lookup"><span data-stu-id="ef919-136">Requirements</span></span>  
 <span data-ttu-id="ef919-137">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef919-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef919-138">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef919-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef919-139">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef919-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef919-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef919-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef919-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ef919-141">See also</span></span>
- [<span data-ttu-id="ef919-142">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ef919-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
