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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148815"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="047ba-102">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="047ba-103">Служит абстрактным базовым интерфейсом для перечислителей, которые используются приложением для отладки.</span><span class="sxs-lookup"><span data-stu-id="047ba-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="047ba-104">Методы</span><span class="sxs-lookup"><span data-stu-id="047ba-104">Methods</span></span>  
  
|<span data-ttu-id="047ba-105">Метод</span><span class="sxs-lookup"><span data-stu-id="047ba-105">Method</span></span>|<span data-ttu-id="047ba-106">Описание</span><span class="sxs-lookup"><span data-stu-id="047ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="047ba-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="047ba-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="047ba-108">Создает копию данного объекта `ICorDebugEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="047ba-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="047ba-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="047ba-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="047ba-110">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="047ba-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="047ba-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="047ba-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="047ba-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="047ba-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="047ba-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="047ba-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="047ba-114">Перемещение курсора вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="047ba-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="047ba-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="047ba-115">Remarks</span></span>  
 <span data-ttu-id="047ba-116">Следующие перечислители являются производными от `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="047ba-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="047ba-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="047ba-118">«ICorDebugAssemblyEnum»</span><span class="sxs-lookup"><span data-stu-id="047ba-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="047ba-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="047ba-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="047ba-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="047ba-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="047ba-123">«ICorDebugErrorInfoEnum»</span><span class="sxs-lookup"><span data-stu-id="047ba-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="047ba-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="047ba-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="047ba-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="047ba-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="047ba-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="047ba-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="047ba-130">«ICorDebugModuleEnum»</span><span class="sxs-lookup"><span data-stu-id="047ba-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="047ba-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="047ba-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="047ba-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="047ba-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="047ba-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="047ba-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="047ba-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="047ba-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="047ba-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="047ba-138">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="047ba-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="047ba-139">Требования</span><span class="sxs-lookup"><span data-stu-id="047ba-139">Requirements</span></span>  
 <span data-ttu-id="047ba-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="047ba-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="047ba-141">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="047ba-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="047ba-142">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="047ba-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="047ba-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="047ba-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047ba-144">См. также</span><span class="sxs-lookup"><span data-stu-id="047ba-144">See also</span></span>

- [<span data-ttu-id="047ba-145">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="047ba-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
