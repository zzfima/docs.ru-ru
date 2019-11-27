---
title: Метод ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439813"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="24fee-102">Метод ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="24fee-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="24fee-103">Уведомляет профилировщик кода о начале сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="24fee-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24fee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24fee-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24fee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24fee-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="24fee-106">окне Общее число записей в массиве `generationCollected`.</span><span class="sxs-lookup"><span data-stu-id="24fee-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="24fee-107">окне Массив логических значений, которые `true`, если в ходе этой сборки мусора будет собираться поколение, соответствующее индексу массива; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="24fee-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="24fee-108">Массив индексируется по значению перечисления [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) , которое указывает на поколение.</span><span class="sxs-lookup"><span data-stu-id="24fee-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="24fee-109">окне Значение перечисления [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) , указывающее причину принудительной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="24fee-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24fee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="24fee-110">Remarks</span></span>  
 <span data-ttu-id="24fee-111">Все обратные вызовы, относящиеся к этой сборке мусора, будут происходить между обратным вызовом `GarbageCollectionStarted` и соответствующим обратным вызовом [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="24fee-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="24fee-112">Эти обратные вызовы не должны выполняться в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="24fee-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="24fee-113">Профилировщик может быть в безопасности проверять объекты в их исходных расположениях во время обратного вызова `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="24fee-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="24fee-114">Сборщик мусора начнет перемещать объекты после возврата из `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="24fee-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="24fee-115">После возвращения профилировщика из этого обратного вызова профилировщик должен считать, что все идентификаторы объектов являются недопустимыми, пока не получит ответный вызов `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="24fee-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24fee-116">Требования</span><span class="sxs-lookup"><span data-stu-id="24fee-116">Requirements</span></span>  
 <span data-ttu-id="24fee-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24fee-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24fee-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24fee-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24fee-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24fee-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24fee-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24fee-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fee-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="24fee-121">See also</span></span>

- [<span data-ttu-id="24fee-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="24fee-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="24fee-123">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="24fee-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
