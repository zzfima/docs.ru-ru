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
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124065"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="8a087-102">Интерфейс ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="8a087-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="8a087-103">Представляет кадр текущего стека.</span><span class="sxs-lookup"><span data-stu-id="8a087-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a087-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8a087-104">Methods</span></span>  
  
|<span data-ttu-id="8a087-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8a087-105">Method</span></span>|<span data-ttu-id="8a087-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8a087-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a087-107">Метод CreateStepper</span><span class="sxs-lookup"><span data-stu-id="8a087-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="8a087-108">Возвращает объект ICorDebugStepper для выполнения операций с заходом относительно этого `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8a087-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="8a087-109">Метод GetCallee</span><span class="sxs-lookup"><span data-stu-id="8a087-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="8a087-110">Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.</span><span class="sxs-lookup"><span data-stu-id="8a087-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8a087-111">Метод GetCaller</span><span class="sxs-lookup"><span data-stu-id="8a087-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="8a087-112">Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внешняя рамка в цепочке.</span><span class="sxs-lookup"><span data-stu-id="8a087-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8a087-113">Метод GetChain</span><span class="sxs-lookup"><span data-stu-id="8a087-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="8a087-114">Возвращает указатель на ICorDebugChain, частью которого является этот `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8a087-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="8a087-115">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="8a087-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="8a087-116">Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="8a087-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8a087-117">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="8a087-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="8a087-118">Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="8a087-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8a087-119">Метод GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="8a087-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="8a087-120">Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="8a087-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8a087-121">Метод GetStackRange</span><span class="sxs-lookup"><span data-stu-id="8a087-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="8a087-122">Возвращает диапазон абсолютных адресов кадра стека, представленного данным `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="8a087-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a087-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a087-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a087-124">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8a087-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a087-125">Требования</span><span class="sxs-lookup"><span data-stu-id="8a087-125">Requirements</span></span>  
 <span data-ttu-id="8a087-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a087-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a087-127">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a087-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a087-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a087-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a087-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a087-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a087-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8a087-130">See also</span></span>

- [<span data-ttu-id="8a087-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8a087-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
