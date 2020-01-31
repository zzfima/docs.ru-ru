---
title: Метод ICorProfilerCallback4::SurvivingReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: bec50183e6a8690cb02f3dc06d32b7449e055cea
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865172"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="d60f5-102">Метод ICorProfilerCallback4::SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="d60f5-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="d60f5-103">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="d60f5-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="d60f5-104">Этот метод вызывается, если профилировщик реализовал интерфейс [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d60f5-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="d60f5-105">Этот обратный вызов заменяет метод [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , так как он может сообщать о больших диапазонах объектов, длина которых превышает то, что может быть выражено в ulong.</span><span class="sxs-lookup"><span data-stu-id="d60f5-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60f5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d60f5-106">Syntax</span></span>  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60f5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d60f5-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="d60f5-108">[in] Количество блоков смежных объектов, оставшихся в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="d60f5-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="d60f5-109">То есть значение `cSurvivingObjectIDRanges` является размером массивов `objectIDRangeStart` и `cObjectIDRangeLength`, в которых хранятся идентификаторы `ObjectID` и длины каждого блока объектов соответственно.</span><span class="sxs-lookup"><span data-stu-id="d60f5-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="d60f5-110">Следующие два аргумента `SurvivingReferences2` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="d60f5-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="d60f5-111">Иными словами, `objectIDRangeStart` и `cObjectIDRangeLength` относятся к одному и тому же блоку смежных объектов.</span><span class="sxs-lookup"><span data-stu-id="d60f5-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="d60f5-112">[in] Массив значений `ObjectID`, каждое из которых является начальным адресом блока смежных активных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="d60f5-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="d60f5-113">[in] Массив целых чисел, каждое из которых представляет размер оставшегося блока смежных объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="d60f5-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="d60f5-114">Размер указывается для каждого блока, ссылка на который имеется в массиве `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="d60f5-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d60f5-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="d60f5-115">Remarks</span></span>  
 <span data-ttu-id="d60f5-116">Для определения того, уцелел ли объект после сборки мусора, элементы массивов `objectIDRangeStart` и `cObjectIDRangeLength` должны интерпретироваться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d60f5-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="d60f5-117">Предположим, что значение `ObjectID` (`ObjectID`) находится в следующем диапазоне:</span><span class="sxs-lookup"><span data-stu-id="d60f5-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="d60f5-118">При любом значении `i`, находящемся в указанном ниже диапазоне, объект уцелел после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d60f5-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="d60f5-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="d60f5-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="d60f5-120">Сборка мусора без сжатия освобождает память, занятую "мертвыми" объектами, но не сжимает освобожденное пространство.</span><span class="sxs-lookup"><span data-stu-id="d60f5-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="d60f5-121">В результате этого память возвращается в кучу, но активные объекты не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="d60f5-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="d60f5-122">Среда CLR вызывает метод `SurvivingReferences2` для выполнения сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="d60f5-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="d60f5-123">Для сжатия сборок мусора вместо нее вызывается [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d60f5-123">For compacting garbage collections, [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="d60f5-124">Отдельная операция сборки мусора может предусматривать сжатие для одного поколения и не предусматривать — для другого.</span><span class="sxs-lookup"><span data-stu-id="d60f5-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="d60f5-125">Для сборки мусора в любом конкретном поколении профилировщик получит либо `SurvivingReferences2` обратный вызов, либо обратный вызов [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) , но не оба.</span><span class="sxs-lookup"><span data-stu-id="d60f5-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="d60f5-126">Несколько обратных вызовов `SurvivingReferences2` может быть получено в ходе определенной сборки мусора из-за ограниченной внутренней буферизации, нескольких обратных вызовов во время сборки мусора на сервере и по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="d60f5-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="d60f5-127">При получении нескольких обратных вызовов во время сборки мусора информация накапливается — все ссылки, сообщаемые в обратных вызовах `SurvivingReferences2`, сохранятся после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d60f5-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="d60f5-128">Если профилировщик реализует интерфейсы [ICorProfilerCallback](icorprofilercallback-interface.md) и [ICorProfilerCallback4](icorprofilercallback4-interface.md) , метод `SurvivingReferences2` вызывается перед методом [ICorProfilerCallback2:: SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) , но только при успешном возврате `SurvivingReferences2`.</span><span class="sxs-lookup"><span data-stu-id="d60f5-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="d60f5-129">Профилировщики могут возвращать значение HRESULT, указывающее на сбой метода `SurvivingReferences2`, что позволяет избежать вызова второго метода.</span><span class="sxs-lookup"><span data-stu-id="d60f5-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60f5-130">Требования</span><span class="sxs-lookup"><span data-stu-id="d60f5-130">Requirements</span></span>  
 <span data-ttu-id="d60f5-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d60f5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60f5-132">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d60f5-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d60f5-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d60f5-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d60f5-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60f5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60f5-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="d60f5-135">See also</span></span>

- [<span data-ttu-id="d60f5-136">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d60f5-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d60f5-137">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="d60f5-137">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="d60f5-138">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="d60f5-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
