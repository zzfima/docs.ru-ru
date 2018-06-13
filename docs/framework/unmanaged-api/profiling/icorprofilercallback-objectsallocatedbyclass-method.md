---
title: Метод ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454356"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="0788a-102">Метод ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="0788a-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="0788a-103">Уведомляет профилировщик о количестве экземпляров каждого заданного класса, которые были созданы после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0788a-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0788a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0788a-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0788a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0788a-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="0788a-106">[in] Размер `classIds` и `cObjects` массивов.</span><span class="sxs-lookup"><span data-stu-id="0788a-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="0788a-107">[in] Массив идентификаторов класса, где каждый идентификатор определяет класс с одним или несколькими экземплярами.</span><span class="sxs-lookup"><span data-stu-id="0788a-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="0788a-108">[in] Массив целых чисел, где каждое целое число задает количество экземпляров для классом-аналогом в `classIds` массива.</span><span class="sxs-lookup"><span data-stu-id="0788a-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0788a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0788a-109">Remarks</span></span>  
 <span data-ttu-id="0788a-110">`classIds` И `cObjects` массивы являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="0788a-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="0788a-111">Например `classIds[i]` и `cObjects[i]` ссылаются на том же классе.</span><span class="sxs-lookup"><span data-stu-id="0788a-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="0788a-112">Если с момента предыдущей сборки мусора будет создан экземпляр класса, класс пропускается.</span><span class="sxs-lookup"><span data-stu-id="0788a-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="0788a-113">`ObjectsAllocatedByClass` Обратного вызова не будут передавать объектов, помещенных в кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="0788a-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="0788a-114">Сообщаемые номера `ObjectsAllocatedByClass` представляют собой только оценки.</span><span class="sxs-lookup"><span data-stu-id="0788a-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="0788a-115">Точное количество использовать [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="0788a-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="0788a-116">`classIds` Массив может содержать один или несколько элементы со значением null, если соответствующий `cObjects` массив содержит типы, которые выгрузки.</span><span class="sxs-lookup"><span data-stu-id="0788a-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0788a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0788a-117">Requirements</span></span>  
 <span data-ttu-id="0788a-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0788a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0788a-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0788a-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0788a-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0788a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0788a-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0788a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0788a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0788a-122">See Also</span></span>  
 [<span data-ttu-id="0788a-123">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0788a-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
