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
ms.openlocfilehash: c037f2509aaa0a5e4c3f7a844614742b6f21bec3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769139"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="57631-102">Метод ICorProfilerCallback::MovedReferences</span><span class="sxs-lookup"><span data-stu-id="57631-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="57631-103">Вызывается для предоставления сведений о структуре объектов в куче в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="57631-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57631-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57631-104">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="57631-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57631-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="57631-106">[in] Количество блоков смежных объектов, перемещенных в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="57631-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="57631-107">Таким образом значение `cMovedObjectIDRanges` представляет общий размер массивов `oldObjectIDRangeStart`, `newObjectIDRangeStart` и `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="57631-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="57631-108">Следующие три аргумента `MovedReferences` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="57631-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="57631-109">Другими словами, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` и `cObjectIDRangeLength[i]` относятся к одному и тому же блоку смежных объектов.</span><span class="sxs-lookup"><span data-stu-id="57631-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="57631-110">[in] Массив значений `ObjectID`, каждое из которых является старым (до сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="57631-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="57631-111">[in] Массив значений `ObjectID`, каждое из которых является новым (после сборки мусора) начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="57631-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="57631-112">[in] Массив целых чисел, каждое из которых представляет размер блока смежных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="57631-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="57631-113">Размер указывается для каждого блока, ссылка на который имеется в массивах `oldObjectIDRangeStart` и `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="57631-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57631-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="57631-114">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57631-115">Этот метод сообщает размеры как `MAX_ULONG` для объектов с размером более 4 Гб на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="57631-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="57631-116">Чтобы получить размер объектов, размер которых превышает 4 ГБ, используйте [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="57631-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="57631-117">Сжатие сборки мусора без сжатия освобождает память, занятую "мертвыми" объектами, и сжимает это освобожденное пространство.</span><span class="sxs-lookup"><span data-stu-id="57631-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="57631-118">В результате динамические объекты могут быть перемещены в кучу, и значения `ObjectID`, распространенные предыдущими уведомлениями, могут измениться.</span><span class="sxs-lookup"><span data-stu-id="57631-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="57631-119">Предположим, что существующее значение `ObjectID` (`oldObjectID`) находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="57631-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="57631-120">В этом случае смещение от начала диапазона к началу объекта следующее:</span><span class="sxs-lookup"><span data-stu-id="57631-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="57631-121">Для любого значения параметра `i`, который находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="57631-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="57631-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="57631-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="57631-123">можно вычислить новый `ObjectID` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="57631-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="57631-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="57631-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="57631-125">Ни одно из значений `ObjectID`, переданных `MovedReferences`, не является допустимым во время самого обратного вызова, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="57631-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="57631-126">В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `MovedReferences`.</span><span class="sxs-lookup"><span data-stu-id="57631-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="57631-127">Объект [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) обратный вызов указывает, что все объекты были перемещены в новые расположения и можно выполнять проверку.</span><span class="sxs-lookup"><span data-stu-id="57631-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57631-128">Требования</span><span class="sxs-lookup"><span data-stu-id="57631-128">Requirements</span></span>  
 <span data-ttu-id="57631-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57631-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57631-130">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57631-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57631-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57631-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57631-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57631-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57631-133">См. также</span><span class="sxs-lookup"><span data-stu-id="57631-133">See also</span></span>

- [<span data-ttu-id="57631-134">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="57631-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="57631-135">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="57631-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="57631-136">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="57631-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="57631-137">Профилирование</span><span class="sxs-lookup"><span data-stu-id="57631-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
