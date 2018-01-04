---
title: "Интерфейс ICorProfilerModuleEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b337bc99f89b04145afb3994da840cff7e2c5c80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="95c3f-102">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="95c3f-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="95c3f-103">Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="95c3f-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95c3f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="95c3f-104">Methods</span></span>  
  
|<span data-ttu-id="95c3f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="95c3f-105">Method</span></span>|<span data-ttu-id="95c3f-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="95c3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95c3f-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="95c3f-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="95c3f-108">Получает указатель на копию этого интерфейса `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="95c3f-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="95c3f-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="95c3f-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="95c3f-110">Возвращает число управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="95c3f-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="95c3f-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="95c3f-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="95c3f-112">Возвращает заданное число смежных модулей из последовательной коллекции объектов начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="95c3f-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="95c3f-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="95c3f-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="95c3f-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="95c3f-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="95c3f-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="95c3f-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="95c3f-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="95c3f-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c3f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="95c3f-117">Remarks</span></span>  
 <span data-ttu-id="95c3f-118">Интерфейс `ICorProfilerModuleEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="95c3f-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="95c3f-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="95c3f-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="95c3f-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="95c3f-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c3f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="95c3f-121">Requirements</span></span>  
 <span data-ttu-id="95c3f-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c3f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c3f-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95c3f-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95c3f-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95c3f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95c3f-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c3f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c3f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="95c3f-126">See Also</span></span>  
 [<span data-ttu-id="95c3f-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="95c3f-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="95c3f-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="95c3f-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="95c3f-129">Метод EnumModules</span><span class="sxs-lookup"><span data-stu-id="95c3f-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
