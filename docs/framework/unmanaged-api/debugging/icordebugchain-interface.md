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
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777987"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="efe96-102">Интерфейс ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="efe96-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="efe96-103">Представляет сегмент физического или логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="efe96-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efe96-104">Методы</span><span class="sxs-lookup"><span data-stu-id="efe96-104">Methods</span></span>  
  
|<span data-ttu-id="efe96-105">Метод</span><span class="sxs-lookup"><span data-stu-id="efe96-105">Method</span></span>|<span data-ttu-id="efe96-106">Описание</span><span class="sxs-lookup"><span data-stu-id="efe96-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efe96-107">Метод EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="efe96-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="efe96-108">Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="efe96-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="efe96-109">Метод GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="efe96-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="efe96-110">Возвращает активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="efe96-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="efe96-111">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="efe96-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="efe96-112">Возвращает цепочку, вызванную этой цепочкой.</span><span class="sxs-lookup"><span data-stu-id="efe96-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="efe96-113">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="efe96-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="efe96-114">Возвращает цепочку, вызвавшую эту цепь.</span><span class="sxs-lookup"><span data-stu-id="efe96-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="efe96-115">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="efe96-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="efe96-116">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="efe96-116">Not implemented.</span></span>|  
|[<span data-ttu-id="efe96-117">Метод GetNext</span><span class="sxs-lookup"><span data-stu-id="efe96-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="efe96-118">Возвращает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="efe96-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="efe96-119">Метод GetPrevious</span><span class="sxs-lookup"><span data-stu-id="efe96-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="efe96-120">Возвращает предыдущую цепочку кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="efe96-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="efe96-121">Метод GetReason</span><span class="sxs-lookup"><span data-stu-id="efe96-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="efe96-122">Возвращает причину женесис данной вызывающей цепочки.</span><span class="sxs-lookup"><span data-stu-id="efe96-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="efe96-123">Метод GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="efe96-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="efe96-124">Возвращает набор регистров для активной части этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="efe96-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="efe96-125">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="efe96-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="efe96-126">Возвращает диапазон адресов сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="efe96-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="efe96-127">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="efe96-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="efe96-128">Возвращает физический поток, частью которого является эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="efe96-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="efe96-129">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="efe96-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="efe96-130">Возвращает значение, указывающее, выполняется ли в этой цепочке управляемый код.</span><span class="sxs-lookup"><span data-stu-id="efe96-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efe96-131">Заметки</span><span class="sxs-lookup"><span data-stu-id="efe96-131">Remarks</span></span>  
 <span data-ttu-id="efe96-132">Кадры стека в цепочке занимают непрерывное пространство стека и совместно используют один и тот же поток и контекст.</span><span class="sxs-lookup"><span data-stu-id="efe96-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="efe96-133">Цепочка может представлять как управляемые, так и неуправляемые цепочки кода.</span><span class="sxs-lookup"><span data-stu-id="efe96-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="efe96-134">Пустой экземпляр `ICorDebugChain` представляет неуправляемую цепочку кода.</span><span class="sxs-lookup"><span data-stu-id="efe96-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efe96-135">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="efe96-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe96-136">Требования</span><span class="sxs-lookup"><span data-stu-id="efe96-136">Requirements</span></span>  
 <span data-ttu-id="efe96-137">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efe96-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efe96-138">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efe96-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efe96-139">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efe96-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efe96-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efe96-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe96-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="efe96-141">See also</span></span>

- [<span data-ttu-id="efe96-142">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="efe96-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
