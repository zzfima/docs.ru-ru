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
ms.openlocfilehash: 4229332ef3a079a5a294e27b624dde0e1fb46691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782955"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="a4ca8-102">Метод ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="a4ca8-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="a4ca8-103">Уведомляет профилировщик о количестве экземпляров каждого заданного класса, которые были созданы после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ca8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4ca8-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4ca8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4ca8-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="a4ca8-106">[in] Размер `classIds` и `cObjects` массивов.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="a4ca8-107">[in] Массив идентификаторов класса, где каждый идентификатор определяет класс с одним или несколькими экземплярами.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="a4ca8-108">[in] Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в `classIds` массива.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4ca8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4ca8-109">Remarks</span></span>  
 <span data-ttu-id="a4ca8-110">`classIds` И `cObjects` массивы являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="a4ca8-111">Например `classIds[i]` и `cObjects[i]` ссылаться на тот же класс.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="a4ca8-112">Если с момента предыдущей сборки мусора был создан экземпляр класса, класс пропускается.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="a4ca8-113">`ObjectsAllocatedByClass` Обратный вызов не будет выдавать объектов, помещенных в кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="a4ca8-114">Сообщаемое номера `ObjectsAllocatedByClass` только приблизительные.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="a4ca8-115">Для точного подсчета строк, используйте [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="a4ca8-116">`classIds` Массив может содержать один или несколько записи со значением null, если соответствующий `cObjects` массив содержит типы, которые выгрузки.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ca8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a4ca8-117">Requirements</span></span>  
 <span data-ttu-id="a4ca8-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ca8-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4ca8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4ca8-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4ca8-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ca8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a4ca8-122">See also</span></span>

- [<span data-ttu-id="a4ca8-123">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a4ca8-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
