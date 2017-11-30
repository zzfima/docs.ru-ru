---
title: "Метод ICorProfilerCallback2::GarbageCollectionStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="e0330-102">Метод ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="e0330-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="e0330-103">Уведомляет профилировщик кода о начале сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e0330-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0330-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0330-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0330-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0330-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="e0330-106">[in] Общее количество записей в `generationCollected` массива.</span><span class="sxs-lookup"><span data-stu-id="e0330-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="e0330-107">[in] Массив логических значений, которые являются `true` поколение, для которого соответствует индексу массива осуществляется, собранных в ходе этой сборке мусора, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="e0330-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="e0330-108">Массив индексируется значением [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) перечисления, которое задает поколение.</span><span class="sxs-lookup"><span data-stu-id="e0330-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="e0330-109">[in] Значение [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) перечисления, указывающее причину сборка мусора была вызвана.</span><span class="sxs-lookup"><span data-stu-id="e0330-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0330-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0330-110">Remarks</span></span>  
 <span data-ttu-id="e0330-111">Все обратные вызовы, которые относятся к этой сборке мусора будет выполняться между `GarbageCollectionStarted` обратного вызова и соответствующий [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e0330-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="e0330-112">Эти обратные вызовы должны осуществляться в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="e0330-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="e0330-113">Безопасно для профилировщика для проверки объектов в их исходное расположение во время `GarbageCollectionStarted` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e0330-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="e0330-114">Сборщик мусора начнет перемещение объектов после возврата из `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="e0330-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="e0330-115">Рекомендуется после возврата профилировщика из этого обратного вызова профилировщика все идентификаторы объектов недействительным, пока не получит `ICorProfilerCallback2::GarbageCollectionFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e0330-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0330-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e0330-116">Requirements</span></span>  
 <span data-ttu-id="e0330-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0330-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0330-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0330-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0330-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0330-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0330-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0330-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0330-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e0330-121">See Also</span></span>  
 [<span data-ttu-id="e0330-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e0330-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e0330-123">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="e0330-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
