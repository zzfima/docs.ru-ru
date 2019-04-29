---
title: Интерфейс ICorProfilerThreadEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 47359cd71460732100364f07e0dc5efacc44c760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597443"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="be6e4-102">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="be6e4-102">ICorProfilerThreadEnum Interface</span></span>
<span data-ttu-id="be6e4-103">Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="be6e4-103">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be6e4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="be6e4-104">Methods</span></span>  
  
|<span data-ttu-id="be6e4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="be6e4-105">Method</span></span>|<span data-ttu-id="be6e4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="be6e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be6e4-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="be6e4-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="be6e4-108">Получает указатель на копию этого интерфейса `ICorProfilerThreadEnum`.</span><span class="sxs-lookup"><span data-stu-id="be6e4-108">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="be6e4-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="be6e4-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="be6e4-110">Возвращает число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="be6e4-110">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="be6e4-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="be6e4-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-next-method.md)|<span data-ttu-id="be6e4-112">Возвращает заданное число смежных потоков из упорядоченной коллекции потоков начиная с текущей позиции перечислителя в последовательности.</span><span class="sxs-lookup"><span data-stu-id="be6e4-112">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="be6e4-113">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="be6e4-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="be6e4-114">Перемещает курсор перечислителя в начальную позицию последовательности.</span><span class="sxs-lookup"><span data-stu-id="be6e4-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="be6e4-115">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="be6e4-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="be6e4-116">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="be6e4-116">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be6e4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="be6e4-117">Remarks</span></span>  
 <span data-ttu-id="be6e4-118">Интерфейс `ICorProfilerThreadEnum` является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="be6e4-118">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="be6e4-119">Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью.</span><span class="sxs-lookup"><span data-stu-id="be6e4-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="be6e4-120">Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.</span><span class="sxs-lookup"><span data-stu-id="be6e4-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6e4-121">Требования</span><span class="sxs-lookup"><span data-stu-id="be6e4-121">Requirements</span></span>  
 <span data-ttu-id="be6e4-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be6e4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6e4-123">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be6e4-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be6e4-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be6e4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be6e4-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6e4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6e4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="be6e4-126">See also</span></span>

- [<span data-ttu-id="be6e4-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="be6e4-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="be6e4-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="be6e4-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
