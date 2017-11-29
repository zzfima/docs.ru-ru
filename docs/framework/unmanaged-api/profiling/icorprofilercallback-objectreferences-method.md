---
title: "Метод ICorProfilerCallback::ObjectReferences"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5cdebc1984f86d3801759f8f987df8fb89d82e3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="99961-102">Метод ICorProfilerCallback::ObjectReferences</span><span class="sxs-lookup"><span data-stu-id="99961-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="99961-103">Уведомляет профилировщик об объектах в памяти, на которые ссылаются заданным объектом.</span><span class="sxs-lookup"><span data-stu-id="99961-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99961-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99961-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99961-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="99961-106">[in] Идентификатор объекта, который ссылается на объекты.</span><span class="sxs-lookup"><span data-stu-id="99961-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="99961-107">[in] Идентификатор, указанный объект является экземпляром класса.</span><span class="sxs-lookup"><span data-stu-id="99961-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="99961-108">[in] Число объектов ссылается указанный объект (то есть, количество элементов в `objectRefIds` массива).</span><span class="sxs-lookup"><span data-stu-id="99961-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="99961-109">[in] Массив идентификаторов объектов, на которые ссылаются по `objectId`.</span><span class="sxs-lookup"><span data-stu-id="99961-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99961-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="99961-110">Remarks</span></span>  
 <span data-ttu-id="99961-111">`ObjectReferences` Метод вызывается для каждого объекта, оставшихся в куче после завершения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="99961-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="99961-112">Если профилировщик возвращает сообщение об ошибке из этого обратного вызова, профилирующей службы перестанет работать, вызов этого обратного вызова до следующей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="99961-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="99961-113">`ObjectReferences` Обратного вызова можно использовать в сочетании с [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) обратного вызова, чтобы создать граф ссылок полный объект среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="99961-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="99961-114">Общеязыковая среда выполнения (CLR) гарантирует, что каждая ссылка объекта выводится только один раз `ObjectReferences` метод.</span><span class="sxs-lookup"><span data-stu-id="99961-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="99961-115">Идентификаторы объектов, возвращенных `ObjectReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов.</span><span class="sxs-lookup"><span data-stu-id="99961-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="99961-116">Таким образом, профилировщик должен не пытаться проверять объекты во время `ObjectReferences` вызова.</span><span class="sxs-lookup"><span data-stu-id="99961-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="99961-117">Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) вызывается сборке мусора коллекции завершена, и можно безопасно выполнить проверку.</span><span class="sxs-lookup"><span data-stu-id="99961-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="99961-118">Значение null `ClassId` указывает, что `objectId` имеет тип, который будет выгружен.</span><span class="sxs-lookup"><span data-stu-id="99961-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99961-119">Требования</span><span class="sxs-lookup"><span data-stu-id="99961-119">Requirements</span></span>  
 <span data-ttu-id="99961-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99961-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99961-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99961-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99961-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99961-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99961-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99961-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99961-124">См. также</span><span class="sxs-lookup"><span data-stu-id="99961-124">See Also</span></span>  
 [<span data-ttu-id="99961-125">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="99961-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
