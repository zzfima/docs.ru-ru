---
title: "Метод ICorProfilerInfo2::GetObjectGeneration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetObjectGeneration
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e90139f96638dbb1a183f98e754838ff52424fc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="569ac-102">Метод ICorProfilerInfo2::GetObjectGeneration</span><span class="sxs-lookup"><span data-stu-id="569ac-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="569ac-103">Возвращает сегмент кучи, содержащей указанный объект.</span><span class="sxs-lookup"><span data-stu-id="569ac-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="569ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="569ac-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="569ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="569ac-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="569ac-106">[in] Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="569ac-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="569ac-107">[out] Указатель на [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуру, которая описывает диапазон (т. е., блок) памяти в поколении, для которого выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="569ac-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="569ac-108">Этот диапазон содержит указанный объект.</span><span class="sxs-lookup"><span data-stu-id="569ac-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="569ac-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="569ac-109">Remarks</span></span>  
 <span data-ttu-id="569ac-110">`GetObjectGeneration` Метод можно вызывать из любого обратного вызова профилировщика при условии, что сборщик мусора не выполняется.</span><span class="sxs-lookup"><span data-stu-id="569ac-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="569ac-111">То есть, он может вызываться из любого обратного вызова, за исключением тех, которые происходят между [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) и [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="569ac-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="569ac-112">Требования</span><span class="sxs-lookup"><span data-stu-id="569ac-112">Requirements</span></span>  
 <span data-ttu-id="569ac-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="569ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="569ac-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="569ac-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="569ac-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="569ac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="569ac-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="569ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="569ac-117">См. также</span><span class="sxs-lookup"><span data-stu-id="569ac-117">See Also</span></span>  
 [<span data-ttu-id="569ac-118">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="569ac-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="569ac-119">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="569ac-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
