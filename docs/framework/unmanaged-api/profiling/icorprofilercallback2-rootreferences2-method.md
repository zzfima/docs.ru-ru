---
title: Метод ICorProfilerCallback2::RootReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09616243aef272be041573864effd25017cc65c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082156"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="4c5f6-102">Метод ICorProfilerCallback2::RootReferences2</span><span class="sxs-lookup"><span data-stu-id="4c5f6-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="4c5f6-103">Уведомляет профилировщик о корневыми ссылками, после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="4c5f6-104">Этот метод является расширением [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c5f6-105">Syntax</span></span>  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c5f6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c5f6-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="4c5f6-107">[in] Число элементов в `rootRefIds`, `rootKinds`, `rootFlags`, и `rootIds` массивов.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="4c5f6-108">[in] Массив идентификаторов объектов, каждый из которых ссылается на статический объект или объект в стеке.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="4c5f6-109">Элементы в `rootKinds` массива предоставляют сведения для классификации соответствующих элементов в `rootRefIds` массива.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="4c5f6-110">[in] Массив [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) значения, указывающие тип корня сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="4c5f6-111">[in] Массив [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) значения, описывающие свойства корня сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="4c5f6-112">[in] Массив UINT_PTR значений, которые указывают на целое число, содержащий дополнительные сведения о корне сборки мусора, в зависимости от значения `rootKinds` параметра.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="4c5f6-113">Тип корня представляет собой стек, корневой является ли идентификатор для функции, содержащую нужную переменную.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="4c5f6-114">Если идентификатор корня равен 0, функция является безымянной внутренней среде CLR.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="4c5f6-115">Если тип корневого элемента является дескриптором, идентификатор корня соответствует дескриптору сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="4c5f6-116">Для других типов корня идентификатор является непрозрачным значением и его следует игнорировать.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c5f6-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c5f6-117">Remarks</span></span>  
 <span data-ttu-id="4c5f6-118">`rootRefIds`, `rootKinds`, `rootFlags`, И `rootIds` массивы являются параллельными массивами.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="4c5f6-119">То есть `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, и `rootIds[i]` относятся таким же корнем.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="4c5f6-120">Оба `RootReferences` и `RootReferences2` вызываемые для уведомления профилировщика.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="4c5f6-121">Обычно профилировщик реализует один метод или другой, но не оба, так как данные, передаваемые `RootReferences2` является надмножеством информации, переданной в `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="4c5f6-122">Возможно, для операций в `rootRefIds` должно быть равно нулю, что означает, что соответствующая ссылка корневой имеет значение null и не ссылается на объект в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="4c5f6-123">Идентификаторы объектов, возвращенных `RootReferences2` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старого адреса в новые адреса.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="4c5f6-124">В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="4c5f6-125">Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) является именем, все объекты были перемещены в новые расположения и можно безопасно проверить.</span><span class="sxs-lookup"><span data-stu-id="4c5f6-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c5f6-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4c5f6-126">Requirements</span></span>  
 <span data-ttu-id="4c5f6-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c5f6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c5f6-128">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c5f6-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c5f6-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c5f6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c5f6-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c5f6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5f6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4c5f6-131">See also</span></span>

- [<span data-ttu-id="4c5f6-132">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4c5f6-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4c5f6-133">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="4c5f6-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
