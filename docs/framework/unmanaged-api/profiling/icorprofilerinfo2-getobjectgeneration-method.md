---
title: Метод ICorProfilerInfo2::GetObjectGeneration
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 729ae390d36f82cbafd46385b396d6513489628e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474810"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="2111e-102">Метод ICorProfilerInfo2::GetObjectGeneration</span><span class="sxs-lookup"><span data-stu-id="2111e-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="2111e-103">Возвращает сегмент кучи, который содержит указанный объект.</span><span class="sxs-lookup"><span data-stu-id="2111e-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2111e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2111e-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2111e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2111e-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="2111e-106">[in] Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="2111e-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="2111e-107">[out] Указатель на [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуру, которая описывает диапазон (то есть блок) памяти в поколении, для которого выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="2111e-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="2111e-108">Этот диапазон содержит указанный объект.</span><span class="sxs-lookup"><span data-stu-id="2111e-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2111e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2111e-109">Remarks</span></span>  
 <span data-ttu-id="2111e-110">`GetObjectGeneration` Метод можно вызывать из любого обратного вызова профилировщика при условии, что сборка мусора не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2111e-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="2111e-111">То есть он может вызываться из любого обратного вызова, за исключением тех, которые происходят между [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) и [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="2111e-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2111e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2111e-112">Requirements</span></span>  
 <span data-ttu-id="2111e-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2111e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2111e-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2111e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2111e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2111e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2111e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2111e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2111e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2111e-117">See also</span></span>
- [<span data-ttu-id="2111e-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2111e-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="2111e-119">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2111e-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
