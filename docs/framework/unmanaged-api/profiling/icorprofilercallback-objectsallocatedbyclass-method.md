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
ms.openlocfilehash: 028207486f43e35086ed2e515eb3ae6bca304491
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866082"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="b1c00-102">Метод ICorProfilerCallback::ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="b1c00-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="b1c00-103">Уведомляет профилировщик о количестве экземпляров каждого указанного класса, созданных с момента последнего сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b1c00-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1c00-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1c00-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1c00-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="b1c00-106">окне Размер массивов `classIds` и `cObjects`.</span><span class="sxs-lookup"><span data-stu-id="b1c00-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="b1c00-107">окне Массив идентификаторов классов, где каждый идентификатор указывает класс с одним или несколькими экземплярами.</span><span class="sxs-lookup"><span data-stu-id="b1c00-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="b1c00-108">окне Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в массиве `classIds`.</span><span class="sxs-lookup"><span data-stu-id="b1c00-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1c00-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b1c00-109">Remarks</span></span>  
 <span data-ttu-id="b1c00-110">Массивы `classIds` и `cObjects` являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="b1c00-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="b1c00-111">Например, `classIds[i]` и `cObjects[i]` ссылаются на один и тот же класс.</span><span class="sxs-lookup"><span data-stu-id="b1c00-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="b1c00-112">Если с момента предыдущего сбора мусора экземпляр класса не был создан, класс опускается.</span><span class="sxs-lookup"><span data-stu-id="b1c00-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="b1c00-113">Обратный вызов `ObjectsAllocatedByClass` не будет сообщать объекты, выделенные в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="b1c00-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="b1c00-114">Числа, сообщаемые `ObjectsAllocatedByClass`, являются только оценками.</span><span class="sxs-lookup"><span data-stu-id="b1c00-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="b1c00-115">Для точного числа счетчиков используйте параметр [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="b1c00-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="b1c00-116">Массив `classIds` может содержать одну или несколько записей null, если в соответствующем массиве `cObjects` имеются типы, выгрузка которых выполняется.</span><span class="sxs-lookup"><span data-stu-id="b1c00-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c00-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b1c00-117">Requirements</span></span>  
 <span data-ttu-id="b1c00-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1c00-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1c00-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1c00-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1c00-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1c00-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1c00-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1c00-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c00-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1c00-122">See also</span></span>

- [<span data-ttu-id="b1c00-123">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b1c00-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
