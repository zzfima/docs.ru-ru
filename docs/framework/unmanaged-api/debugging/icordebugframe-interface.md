---
title: Интерфейс ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988758"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="900bc-102">Интерфейс ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="900bc-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="900bc-103">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="900bc-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="900bc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="900bc-104">Methods</span></span>  
  
|<span data-ttu-id="900bc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="900bc-105">Method</span></span>|<span data-ttu-id="900bc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="900bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="900bc-107">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="900bc-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="900bc-108">Получает ICorDebugStepper осуществлять пошаговое выполнение операций относительно данного `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="900bc-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="900bc-109">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="900bc-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="900bc-110">Возвращает указатель на `ICorDebugFrame` в текущей цепи, что вызван этот кадр или возвращает значение null, если данный является самой внутренней рамке в цепочке.</span><span class="sxs-lookup"><span data-stu-id="900bc-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="900bc-111">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="900bc-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="900bc-112">Возвращает указатель на `ICorDebugFrame` в текущей цепи, вызван этот кадр или возвращает значение null, если данный является самым крайним кадром в цепочке.</span><span class="sxs-lookup"><span data-stu-id="900bc-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="900bc-113">Метод GetChain</span><span class="sxs-lookup"><span data-stu-id="900bc-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="900bc-114">Возвращает указатель на ICorDebugChain это `ICorDebugFrame` является частью.</span><span class="sxs-lookup"><span data-stu-id="900bc-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="900bc-115">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="900bc-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="900bc-116">Возвращает указатель на интерфейс ICorDebugCode, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="900bc-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="900bc-117">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="900bc-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="900bc-118">Возвращает указатель на ICorDebugFunction, который содержит код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="900bc-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="900bc-119">Метод GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="900bc-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="900bc-120">Получает маркер метаданных для функции, которая содержит код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="900bc-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="900bc-121">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="900bc-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="900bc-122">Возвращает диапазон абсолютных адресов кадра стека, представленный этим `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="900bc-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="900bc-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="900bc-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="900bc-124">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="900bc-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="900bc-125">Требования</span><span class="sxs-lookup"><span data-stu-id="900bc-125">Requirements</span></span>  
 <span data-ttu-id="900bc-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="900bc-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900bc-127">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="900bc-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="900bc-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="900bc-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="900bc-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900bc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900bc-130">См. также</span><span class="sxs-lookup"><span data-stu-id="900bc-130">See also</span></span>

- [<span data-ttu-id="900bc-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="900bc-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
