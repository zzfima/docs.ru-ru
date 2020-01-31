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
ms.openlocfilehash: add30952588ace0cbc80191617c37d7222cffee7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864496"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="053cb-102">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="053cb-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="053cb-103">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="053cb-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="053cb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="053cb-104">Methods</span></span>  
  
|<span data-ttu-id="053cb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="053cb-105">Method</span></span>|<span data-ttu-id="053cb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="053cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="053cb-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="053cb-107">Clone Method</span></span>](icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="053cb-108">Получает указатель на копию этого интерфейса `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="053cb-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="053cb-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="053cb-109">GetCount Method</span></span>](icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="053cb-110">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="053cb-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="053cb-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="053cb-111">Next Method</span></span>](icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="053cb-112">Возвращает заданное число смежных функций из последовательной коллекции функций начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="053cb-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="053cb-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="053cb-113">Reset Method</span></span>](icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="053cb-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="053cb-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="053cb-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="053cb-115">Skip Method</span></span>](icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="053cb-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="053cb-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053cb-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="053cb-117">Remarks</span></span>  
 <span data-ttu-id="053cb-118">Интерфейс `ICorProfilerFunctionEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="053cb-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="053cb-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="053cb-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="053cb-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="053cb-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="053cb-121">Интерфейс `ICorProfilerFunctionEnum` перечисляет функции, которые уже были скомпилированы для JIT-отладки, но не включает функции, загруженные из собственных образов, созданных с помощью программы Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="053cb-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053cb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="053cb-122">Requirements</span></span>  
 <span data-ttu-id="053cb-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053cb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053cb-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="053cb-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="053cb-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="053cb-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="053cb-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053cb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053cb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="053cb-127">See also</span></span>

- [<span data-ttu-id="053cb-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="053cb-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="053cb-129">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="053cb-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="053cb-130">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="053cb-130">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
