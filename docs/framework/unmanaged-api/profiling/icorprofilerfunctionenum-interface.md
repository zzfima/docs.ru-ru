---
title: "Интерфейс ICorProfilerFunctionEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a3014c8b00cb431c2c5b101e17dc51f49bf73f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="0acc0-102">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="0acc0-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="0acc0-103">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="0acc0-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0acc0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0acc0-104">Methods</span></span>  
  
|<span data-ttu-id="0acc0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0acc0-105">Method</span></span>|<span data-ttu-id="0acc0-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0acc0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0acc0-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="0acc0-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="0acc0-108">Получает указатель на копию этого интерфейса `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="0acc0-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="0acc0-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="0acc0-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="0acc0-110">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="0acc0-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="0acc0-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0acc0-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="0acc0-112">Возвращает заданное число смежных функций из упорядоченной коллекции функций начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="0acc0-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="0acc0-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="0acc0-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="0acc0-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="0acc0-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="0acc0-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="0acc0-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="0acc0-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="0acc0-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0acc0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0acc0-117">Remarks</span></span>  
 <span data-ttu-id="0acc0-118">Интерфейс `ICorProfilerFunctionEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="0acc0-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="0acc0-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="0acc0-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="0acc0-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="0acc0-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="0acc0-121">Интерфейс `ICorProfilerFunctionEnum` перечисляет функции, которые уже были скомпилированы для JIT-отладки, но не включает функции, загруженные из собственных образов, созданных с помощью программы Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="0acc0-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0acc0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0acc0-122">Requirements</span></span>  
 <span data-ttu-id="0acc0-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0acc0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0acc0-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0acc0-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0acc0-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0acc0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0acc0-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0acc0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acc0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0acc0-127">See Also</span></span>  
 [<span data-ttu-id="0acc0-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0acc0-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="0acc0-129">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="0acc0-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="0acc0-130">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="0acc0-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
