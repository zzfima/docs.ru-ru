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
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931985"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="05de1-102">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="05de1-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.</span><span class="sxs-lookup"><span data-stu-id="05de1-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05de1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05de1-104">Methods</span></span>  
  
|<span data-ttu-id="05de1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05de1-105">Method</span></span>|<span data-ttu-id="05de1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05de1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05de1-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="05de1-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="05de1-108">Создает копию этого `ICorDebugEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="05de1-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="05de1-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="05de1-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="05de1-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="05de1-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="05de1-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="05de1-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="05de1-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="05de1-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="05de1-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="05de1-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="05de1-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="05de1-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05de1-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="05de1-115">Remarks</span></span>  
 <span data-ttu-id="05de1-116">Следующие перечислители являются производными `ICorDebugEnum`от:</span><span class="sxs-lookup"><span data-stu-id="05de1-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="05de1-117">"Икордебугаппдомаиненум"</span><span class="sxs-lookup"><span data-stu-id="05de1-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="05de1-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="05de1-119">икордебугблоккингобжектенум</span><span class="sxs-lookup"><span data-stu-id="05de1-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="05de1-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="05de1-121">"Икордебугчаиненум"</span><span class="sxs-lookup"><span data-stu-id="05de1-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="05de1-122">"Икордебугкодинум"</span><span class="sxs-lookup"><span data-stu-id="05de1-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="05de1-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="05de1-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="05de1-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="05de1-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="05de1-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="05de1-128">икордебугхеапенум</span><span class="sxs-lookup"><span data-stu-id="05de1-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="05de1-129">икордебугхеапсегментенум</span><span class="sxs-lookup"><span data-stu-id="05de1-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="05de1-130">"Икордебугмодулинум"</span><span class="sxs-lookup"><span data-stu-id="05de1-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="05de1-131">"Икордебугобжектенум"</span><span class="sxs-lookup"><span data-stu-id="05de1-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="05de1-132">"Икордебугпроцессенум"</span><span class="sxs-lookup"><span data-stu-id="05de1-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="05de1-133">"Икордебугстепперенум"</span><span class="sxs-lookup"><span data-stu-id="05de1-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="05de1-134">"Икордебугсреаденум"</span><span class="sxs-lookup"><span data-stu-id="05de1-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="05de1-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="05de1-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="05de1-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="05de1-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="05de1-138">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="05de1-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05de1-139">Требования</span><span class="sxs-lookup"><span data-stu-id="05de1-139">Requirements</span></span>  
 <span data-ttu-id="05de1-140">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05de1-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05de1-141">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="05de1-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05de1-142">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="05de1-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05de1-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05de1-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05de1-144">См. также</span><span class="sxs-lookup"><span data-stu-id="05de1-144">See also</span></span>

- [<span data-ttu-id="05de1-145">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05de1-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
