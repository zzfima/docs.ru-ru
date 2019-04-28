---
title: Метод ICorProfilerCallback::MovedReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4611b8c186e0293dae73cee4f9d845bb44c167c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904713"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="f5670-102">Метод ICorProfilerCallback::MovedReferences</span><span class="sxs-lookup"><span data-stu-id="f5670-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="f5670-103">Вызывается для предоставления сведений о структуре объектов в куче в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5670-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5670-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5670-104">Syntax</span></span>  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5670-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5670-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="f5670-106">[in] Количество блоков смежных объектов, перемещенных в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f5670-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="f5670-107">Таким образом значение `cMovedObjectIDRanges` представляет общий размер массивов `oldObjectIDRangeStart`, `newObjectIDRangeStart` и `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="f5670-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="f5670-108">Следующие три аргумента `MovedReferences` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="f5670-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="f5670-109">Другими словами, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` и `cObjectIDRangeLength[i]` относятся к одному и тому же блоку смежных объектов.</span><span class="sxs-lookup"><span data-stu-id="f5670-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="f5670-110">[in] Массив значений `ObjectID`, каждое из которых является старым (до сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f5670-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="f5670-111">[in] Массив значений `ObjectID`, каждое из которых является новым (после сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f5670-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="f5670-112">[in] Массив целых чисел, каждое из которых представляет размер блока смежных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f5670-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="f5670-113">Размер указывается для каждого блока, ссылка на который имеется в массивах `oldObjectIDRangeStart` и `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="f5670-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5670-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5670-114">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5670-115">Этот метод сообщает размеры как `MAX_ULONG` для объектов с размером более 4 Гб на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="f5670-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="f5670-116">Чтобы получить размер объектов, размер которых превышает 4 ГБ, используйте [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f5670-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="f5670-117">Сжатие сборки мусора без сжатия освобождает память, занятую "мертвыми" объектами, и сжимает это освобожденное пространство.</span><span class="sxs-lookup"><span data-stu-id="f5670-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="f5670-118">В результате динамические объекты могут быть перемещены в кучу, и значения `ObjectID`, распространенные предыдущими уведомлениями, могут измениться.</span><span class="sxs-lookup"><span data-stu-id="f5670-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="f5670-119">Предположим, что существующее значение `ObjectID` (`oldObjectID`) находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="f5670-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="f5670-120">В этом случае смещение от начала диапазона к началу объекта следующее:</span><span class="sxs-lookup"><span data-stu-id="f5670-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="f5670-121">Для любого значения параметра `i`, который находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="f5670-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="f5670-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="f5670-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="f5670-123">можно вычислить новый `ObjectID` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5670-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="f5670-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="f5670-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="f5670-125">Ни одно из значений `ObjectID`, переданных `MovedReferences`, не является допустимым во время самого обратного вызова, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="f5670-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="f5670-126">В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `MovedReferences`.</span><span class="sxs-lookup"><span data-stu-id="f5670-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="f5670-127">Объект [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) обратный вызов указывает, что все объекты были перемещены в новые расположения и можно выполнять проверку.</span><span class="sxs-lookup"><span data-stu-id="f5670-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5670-128">Требования</span><span class="sxs-lookup"><span data-stu-id="f5670-128">Requirements</span></span>  
 <span data-ttu-id="f5670-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5670-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5670-130">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5670-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5670-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5670-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5670-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5670-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5670-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f5670-133">See also</span></span>

- [<span data-ttu-id="f5670-134">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f5670-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f5670-135">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="f5670-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="f5670-136">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="f5670-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f5670-137">Профилирование</span><span class="sxs-lookup"><span data-stu-id="f5670-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
