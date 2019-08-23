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
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937004"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="f3c03-102">Интерфейс ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="f3c03-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="f3c03-103">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="f3c03-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3c03-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f3c03-104">Methods</span></span>  
  
|<span data-ttu-id="f3c03-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f3c03-105">Method</span></span>|<span data-ttu-id="f3c03-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f3c03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3c03-107">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="f3c03-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="f3c03-108">Получает объект ICorDebugStepper, выполняющий пошаговые операции по `ICorDebugFrame`отношению к этому.</span><span class="sxs-lookup"><span data-stu-id="f3c03-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="f3c03-109">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="f3c03-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="f3c03-110">Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, который вызвал этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.</span><span class="sxs-lookup"><span data-stu-id="f3c03-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="f3c03-111">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="f3c03-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="f3c03-112">Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это самый внешний кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="f3c03-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="f3c03-113">Метод GetChain</span><span class="sxs-lookup"><span data-stu-id="f3c03-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="f3c03-114">Возвращает указатель на ICorDebugChain `ICorDebugFrame` , частью которого является.</span><span class="sxs-lookup"><span data-stu-id="f3c03-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="f3c03-115">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="f3c03-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="f3c03-116">Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="f3c03-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="f3c03-117">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="f3c03-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="f3c03-118">Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="f3c03-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="f3c03-119">Метод GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="f3c03-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="f3c03-120">Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="f3c03-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="f3c03-121">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="f3c03-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="f3c03-122">Возвращает диапазон абсолютных адресов кадра стека, представленного этим `ICorDebugFrame`объектом.</span><span class="sxs-lookup"><span data-stu-id="f3c03-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3c03-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3c03-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3c03-124">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f3c03-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c03-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f3c03-125">Requirements</span></span>  
 <span data-ttu-id="f3c03-126">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3c03-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c03-127">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f3c03-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3c03-128">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f3c03-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c03-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c03-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c03-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f3c03-130">See also</span></span>

- [<span data-ttu-id="f3c03-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f3c03-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
