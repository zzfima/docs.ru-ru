---
title: "ICorDebugEnum интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum
helpviewer_keywords: ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f6596918819294f0ab68735cec12f9eab8bf83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="13d5b-102">ICorDebugEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="13d5b-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="13d5b-103">Служит абстрактным базовым интерфейсом для перечислителей, которые используются приложением для отладки.</span><span class="sxs-lookup"><span data-stu-id="13d5b-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13d5b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="13d5b-104">Methods</span></span>  
  
|<span data-ttu-id="13d5b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="13d5b-105">Method</span></span>|<span data-ttu-id="13d5b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="13d5b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13d5b-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="13d5b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="13d5b-108">Создает копию объекта `ICorDebugEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="13d5b-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="13d5b-109">GetCount-метод</span><span class="sxs-lookup"><span data-stu-id="13d5b-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="13d5b-110">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="13d5b-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="13d5b-111">Reset-метод</span><span class="sxs-lookup"><span data-stu-id="13d5b-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="13d5b-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="13d5b-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="13d5b-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="13d5b-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="13d5b-114">Перемещение курсора вперед в перечислении указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="13d5b-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13d5b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="13d5b-115">Remarks</span></span>  
 <span data-ttu-id="13d5b-116">Следующие перечислители являются производными от `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="13d5b-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="13d5b-117">«ICorDebugAppDomainEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-118">«ICorDebugAssemblyEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="13d5b-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="13d5b-120">«ICorDebugBreakpointEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-121">«ICorDebugChainEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-122">«ICorDebugCodeEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-123">«ICorDebugErrorInfoEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="13d5b-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="13d5b-125">«ICorDebugFrameEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="13d5b-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="13d5b-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="13d5b-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="13d5b-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="13d5b-130">«ICorDebugModuleEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-131">«ICorDebugObjectEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-132">«ICorDebugProcessEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-133">«ICorDebugStepperEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-134">«ICorDebugThreadEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-135">«ICorDebugTypeEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="13d5b-136">«ICorDebugValueEnum»</span><span class="sxs-lookup"><span data-stu-id="13d5b-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="13d5b-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="13d5b-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="13d5b-138">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="13d5b-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d5b-139">Требования</span><span class="sxs-lookup"><span data-stu-id="13d5b-139">Requirements</span></span>  
 <span data-ttu-id="13d5b-140">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13d5b-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d5b-141">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13d5b-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13d5b-142">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13d5b-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13d5b-143">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d5b-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d5b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="13d5b-144">See Also</span></span>  
 [<span data-ttu-id="13d5b-145">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="13d5b-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
