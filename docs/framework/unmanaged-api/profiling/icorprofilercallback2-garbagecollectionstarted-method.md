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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865783"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="c0fa1-102">Метод ICorProfilerCallback2::GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="c0fa1-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="c0fa1-103">Уведомляет профилировщик кода о начале сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fa1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0fa1-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0fa1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0fa1-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="c0fa1-106">окне Общее число записей в массиве `generationCollected`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="c0fa1-107">окне Массив логических значений, которые `true`, если в ходе этой сборки мусора будет собираться поколение, соответствующее индексу массива; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="c0fa1-108">Массив индексируется по значению перечисления [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , которое указывает на поколение.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="c0fa1-109">окне Значение перечисления [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) , указывающее причину принудительной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0fa1-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0fa1-110">Remarks</span></span>  
 <span data-ttu-id="c0fa1-111">Все обратные вызовы, относящиеся к этой сборке мусора, будут происходить между обратным вызовом `GarbageCollectionStarted` и соответствующим обратным вызовом [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c0fa1-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="c0fa1-112">Эти обратные вызовы не должны выполняться в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="c0fa1-113">Профилировщик может быть в безопасности проверять объекты в их исходных расположениях во время обратного вызова `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="c0fa1-114">Сборщик мусора начнет перемещать объекты после возврата из `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="c0fa1-115">После возвращения профилировщика из этого обратного вызова профилировщик должен считать, что все идентификаторы объектов являются недопустимыми, пока не получит ответный вызов `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0fa1-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c0fa1-116">Requirements</span></span>  
 <span data-ttu-id="c0fa1-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0fa1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0fa1-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0fa1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0fa1-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0fa1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0fa1-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0fa1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fa1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0fa1-121">See also</span></span>

- [<span data-ttu-id="c0fa1-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c0fa1-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c0fa1-123">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c0fa1-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
