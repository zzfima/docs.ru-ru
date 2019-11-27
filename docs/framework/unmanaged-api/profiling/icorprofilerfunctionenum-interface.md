---
title: Интерфейс ICorProfilerFunctionEnum
ms.date: 03/30/2017
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
ms.openlocfilehash: 17f7243096b7ac18e456f8f31196055492015346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447798"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="b083c-102">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="b083c-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="b083c-103">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="b083c-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b083c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b083c-104">Methods</span></span>  
  
|<span data-ttu-id="b083c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b083c-105">Method</span></span>|<span data-ttu-id="b083c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b083c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b083c-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="b083c-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="b083c-108">Получает указатель на копию этого интерфейса `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="b083c-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="b083c-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="b083c-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="b083c-110">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="b083c-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="b083c-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b083c-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="b083c-112">Возвращает заданное число смежных функций из последовательной коллекции функций начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="b083c-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="b083c-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="b083c-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="b083c-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="b083c-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="b083c-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="b083c-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="b083c-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="b083c-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b083c-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="b083c-117">Remarks</span></span>  
 <span data-ttu-id="b083c-118">Интерфейс `ICorProfilerFunctionEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="b083c-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="b083c-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="b083c-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="b083c-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="b083c-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="b083c-121">`ICorProfilerFunctionEnum` перечисляет функции, которые уже были JIT-скомпилированы, но не включают функции, загруженные из образов в машинном кодах, созданных с помощью Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="b083c-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b083c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b083c-122">Requirements</span></span>  
 <span data-ttu-id="b083c-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b083c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b083c-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b083c-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b083c-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b083c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b083c-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b083c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b083c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b083c-127">See also</span></span>

- [<span data-ttu-id="b083c-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b083c-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b083c-129">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b083c-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b083c-130">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="b083c-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
