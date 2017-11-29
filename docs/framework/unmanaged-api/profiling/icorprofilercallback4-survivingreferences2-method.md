---
title: "Метод ICorProfilerCallback4::SurvivingReferences2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.SurvivingReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ced8542d2e84b6c317e20d7ff440e6c159383bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="c24b2-102">Метод ICorProfilerCallback4::SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="c24b2-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="c24b2-103">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="c24b2-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="c24b2-104">Этот метод вызывается, если профилировщик реализует [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c24b2-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="c24b2-105">Этот обратный вызов заменяет [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) метода, так как он может объектах, длина которых превышает нельзя выразить значением типа ULong.</span><span class="sxs-lookup"><span data-stu-id="c24b2-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c24b2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c24b2-106">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c24b2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c24b2-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="c24b2-108">[in] Количество блоков смежных объектов, оставшихся в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="c24b2-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="c24b2-109">То есть значение `cSurvivingObjectIDRanges` является размером массивов `objectIDRangeStart` и `cObjectIDRangeLength`, в которых хранятся идентификаторы `ObjectID` и длины каждого блока объектов соответственно.</span><span class="sxs-lookup"><span data-stu-id="c24b2-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="c24b2-110">Следующие два аргумента `SurvivingReferences2` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="c24b2-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="c24b2-111">Иными словами, `objectIDRangeStart` и `cObjectIDRangeLength` относятся к одному и тому же блоку смежных объектов.</span><span class="sxs-lookup"><span data-stu-id="c24b2-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="c24b2-112">[in] Массив значений `ObjectID`, каждое из которых является начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="c24b2-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="c24b2-113">[in] Массив целых чисел, каждое из которых представляет размер оставшегося блока смежных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="c24b2-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="c24b2-114">Размер указывается для каждого блока, ссылка на который имеется в массиве `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="c24b2-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c24b2-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c24b2-115">Remarks</span></span>  
 <span data-ttu-id="c24b2-116">Для определения того, уцелел ли объект после сборки мусора, элементы массивов `objectIDRangeStart` и `cObjectIDRangeLength` должны интерпретироваться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c24b2-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="c24b2-117">Предположим, что значение `ObjectID` (`ObjectID`) находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="c24b2-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="c24b2-118">При любом значении `i`, находящемся в указанном ниже диапазоне, объект уцелел после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c24b2-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="c24b2-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="c24b2-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="c24b2-120">Сборка мусора без сжатия освобождает память, занятую "мертвыми" объектами, но не сжимает освобожденное пространство.</span><span class="sxs-lookup"><span data-stu-id="c24b2-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="c24b2-121">В результате этого память возвращается в кучу, но активные объекты не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="c24b2-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="c24b2-122">Среда CLR вызывает метод `SurvivingReferences2` для выполнения сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="c24b2-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="c24b2-123">Для мусора со сжатием [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="c24b2-123">For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="c24b2-124">Отдельная операция сборки мусора может предусматривать сжатие для одного поколения и не предусматривать — для другого.</span><span class="sxs-lookup"><span data-stu-id="c24b2-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="c24b2-125">Для сборки мусора для любого конкретного поколения, профилировщик получит либо `SurvivingReferences2` обратного вызова или [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) обратного вызова, но не оба.</span><span class="sxs-lookup"><span data-stu-id="c24b2-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="c24b2-126">Несколько обратных вызовов `SurvivingReferences2` может быть получено в ходе определенной сборки мусора из-за ограниченной внутренней буферизации, нескольких обратных вызовов во время сборки мусора на сервере и по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="c24b2-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="c24b2-127">При получении нескольких обратных вызовов во время сборки мусора информация накапливается — все ссылки, сообщаемые в обратных вызовах `SurvivingReferences2`, сохранятся после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c24b2-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="c24b2-128">Если профилировщик реализует оба [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) и [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейсы, `SurvivingReferences2` метод вызывается перед [ICorProfilerCallback2:: SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) метода, но только если `SurvivingReferences2` возвращает успешно.</span><span class="sxs-lookup"><span data-stu-id="c24b2-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="c24b2-129">Профилировщики могут возвращать значение HRESULT, указывающее на сбой метода `SurvivingReferences2`, что позволяет избежать вызова второго метода.</span><span class="sxs-lookup"><span data-stu-id="c24b2-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c24b2-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c24b2-130">Requirements</span></span>  
 <span data-ttu-id="c24b2-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c24b2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c24b2-132">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c24b2-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c24b2-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c24b2-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c24b2-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c24b2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24b2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c24b2-135">See Also</span></span>  
 [<span data-ttu-id="c24b2-136">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c24b2-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c24b2-137">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c24b2-137">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="c24b2-138">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="c24b2-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
