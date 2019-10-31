---
title: Интерфейс ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085262"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="6049b-102">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="6049b-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.</span><span class="sxs-lookup"><span data-stu-id="6049b-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6049b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6049b-104">Methods</span></span>  
  
|<span data-ttu-id="6049b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6049b-105">Method</span></span>|<span data-ttu-id="6049b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6049b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6049b-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="6049b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="6049b-108">Создает копию этого объекта `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="6049b-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="6049b-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="6049b-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="6049b-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="6049b-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="6049b-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="6049b-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="6049b-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="6049b-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="6049b-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="6049b-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="6049b-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="6049b-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6049b-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="6049b-115">Remarks</span></span>  
 <span data-ttu-id="6049b-116">Следующие перечислители являются производными от `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="6049b-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="6049b-117">"Икордебугаппдомаиненум"</span><span class="sxs-lookup"><span data-stu-id="6049b-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="6049b-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="6049b-119">икордебугблоккингобжектенум</span><span class="sxs-lookup"><span data-stu-id="6049b-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="6049b-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="6049b-121">"Икордебугчаиненум"</span><span class="sxs-lookup"><span data-stu-id="6049b-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="6049b-122">"Икордебугкодинум"</span><span class="sxs-lookup"><span data-stu-id="6049b-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="6049b-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="6049b-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="6049b-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="6049b-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="6049b-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="6049b-128">икордебугхеапенум</span><span class="sxs-lookup"><span data-stu-id="6049b-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="6049b-129">икордебугхеапсегментенум</span><span class="sxs-lookup"><span data-stu-id="6049b-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="6049b-130">"Икордебугмодулинум"</span><span class="sxs-lookup"><span data-stu-id="6049b-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="6049b-131">"Икордебугобжектенум"</span><span class="sxs-lookup"><span data-stu-id="6049b-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="6049b-132">"Икордебугпроцессенум"</span><span class="sxs-lookup"><span data-stu-id="6049b-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="6049b-133">"Икордебугстепперенум"</span><span class="sxs-lookup"><span data-stu-id="6049b-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="6049b-134">"Икордебугсреаденум"</span><span class="sxs-lookup"><span data-stu-id="6049b-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="6049b-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="6049b-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="6049b-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="6049b-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="6049b-138">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6049b-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6049b-139">Требования</span><span class="sxs-lookup"><span data-stu-id="6049b-139">Requirements</span></span>  
 <span data-ttu-id="6049b-140">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6049b-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6049b-141">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6049b-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6049b-142">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6049b-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6049b-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6049b-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6049b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="6049b-144">See also</span></span>

- [<span data-ttu-id="6049b-145">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6049b-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
