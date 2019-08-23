---
title: Интерфейс ICorDebugChain
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
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969302"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="93198-102">Интерфейс ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="93198-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="93198-103">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="93198-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93198-104">Методы</span><span class="sxs-lookup"><span data-stu-id="93198-104">Methods</span></span>  
  
|<span data-ttu-id="93198-105">Метод</span><span class="sxs-lookup"><span data-stu-id="93198-105">Method</span></span>|<span data-ttu-id="93198-106">Описание</span><span class="sxs-lookup"><span data-stu-id="93198-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93198-107">Метод EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="93198-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="93198-108">Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="93198-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="93198-109">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="93198-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="93198-110">Возвращает активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="93198-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="93198-111">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="93198-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="93198-112">Возвращает цепочку, вызванную этой цепочкой.</span><span class="sxs-lookup"><span data-stu-id="93198-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="93198-113">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="93198-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="93198-114">Возвращает цепочку, вызвавшую эту цепь.</span><span class="sxs-lookup"><span data-stu-id="93198-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="93198-115">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="93198-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="93198-116">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="93198-116">Not implemented.</span></span>|  
|[<span data-ttu-id="93198-117">Метод GetNext</span><span class="sxs-lookup"><span data-stu-id="93198-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="93198-118">Возвращает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="93198-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="93198-119">Метод GetPrevious</span><span class="sxs-lookup"><span data-stu-id="93198-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="93198-120">Возвращает предыдущую цепочку кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="93198-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="93198-121">Метод GetReason</span><span class="sxs-lookup"><span data-stu-id="93198-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="93198-122">Возвращает причину женесис данной вызывающей цепочки.</span><span class="sxs-lookup"><span data-stu-id="93198-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="93198-123">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="93198-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="93198-124">Возвращает набор регистров для активной части этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="93198-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="93198-125">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="93198-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="93198-126">Возвращает диапазон адресов сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="93198-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="93198-127">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="93198-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="93198-128">Возвращает физический поток, частью которого является эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="93198-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="93198-129">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="93198-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="93198-130">Возвращает значение, указывающее, выполняется ли в этой цепочке управляемый код.</span><span class="sxs-lookup"><span data-stu-id="93198-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93198-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="93198-131">Remarks</span></span>  
 <span data-ttu-id="93198-132">Кадры стека в цепочке занимают непрерывное пространство стека и совместно используют один и тот же поток и контекст.</span><span class="sxs-lookup"><span data-stu-id="93198-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="93198-133">Цепочка может представлять как управляемые, так и неуправляемые цепочки кода.</span><span class="sxs-lookup"><span data-stu-id="93198-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="93198-134">Пустой `ICorDebugChain` экземпляр представляет собой неуправляемую цепочку кода.</span><span class="sxs-lookup"><span data-stu-id="93198-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93198-135">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="93198-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93198-136">Требования</span><span class="sxs-lookup"><span data-stu-id="93198-136">Requirements</span></span>  
 <span data-ttu-id="93198-137">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93198-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93198-138">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="93198-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93198-139">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="93198-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93198-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93198-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93198-141">См. также</span><span class="sxs-lookup"><span data-stu-id="93198-141">See also</span></span>

- [<span data-ttu-id="93198-142">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="93198-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
