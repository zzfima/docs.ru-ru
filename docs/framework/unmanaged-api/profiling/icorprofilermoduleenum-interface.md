---
title: Интерфейс ICorProfilerModuleEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99db173aa7c6064d9f635412d539cc2d4509b24a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124661"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="0bfb9-102">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="0bfb9-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="0bfb9-103">Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bfb9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0bfb9-104">Methods</span></span>  
  
|<span data-ttu-id="0bfb9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0bfb9-105">Method</span></span>|<span data-ttu-id="0bfb9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0bfb9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bfb9-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="0bfb9-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="0bfb9-108">Получает указатель на копию этого интерфейса `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="0bfb9-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="0bfb9-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="0bfb9-110">Возвращает число управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="0bfb9-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0bfb9-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="0bfb9-112">Возвращает заданное число смежных модулей из последовательной коллекции объектов начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="0bfb9-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="0bfb9-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="0bfb9-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="0bfb9-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="0bfb9-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="0bfb9-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bfb9-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bfb9-117">Remarks</span></span>  
 <span data-ttu-id="0bfb9-118">Интерфейс `ICorProfilerModuleEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="0bfb9-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="0bfb9-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="0bfb9-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bfb9-121">Требования</span><span class="sxs-lookup"><span data-stu-id="0bfb9-121">Requirements</span></span>  
 <span data-ttu-id="0bfb9-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bfb9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bfb9-123">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bfb9-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0bfb9-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bfb9-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bfb9-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bfb9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfb9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0bfb9-126">See also</span></span>

- [<span data-ttu-id="0bfb9-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0bfb9-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0bfb9-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="0bfb9-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0bfb9-129">Метод EnumModules</span><span class="sxs-lookup"><span data-stu-id="0bfb9-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
