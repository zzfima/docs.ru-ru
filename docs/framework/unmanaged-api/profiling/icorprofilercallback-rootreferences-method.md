---
title: "Метод ICorProfilerCallback::RootReferences"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="b185c-102">Метод ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="b185c-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="b185c-103">Уведомляет профилировщик с информацией о корневых ссылках после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b185c-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b185c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b185c-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b185c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b185c-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="b185c-106">[in] Число ссылок в `rootRefIds` массива.</span><span class="sxs-lookup"><span data-stu-id="b185c-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="b185c-107">[in] Массив идентификаторов объектов, которые ссылаются на статический объект или объект в стеке.</span><span class="sxs-lookup"><span data-stu-id="b185c-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b185c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b185c-108">Remarks</span></span>  
 <span data-ttu-id="b185c-109">Оба `RootReferences` и [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) вызывается для уведомления профилировщика.</span><span class="sxs-lookup"><span data-stu-id="b185c-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="b185c-110">Обычно профилировщик реализует один из них, но не одновременно, так как сведения передаются в `RootReferences2` является надмножеством переданный `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="b185c-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="b185c-111">Существует возможность `rootRefIds` массива содержит пустой объект.</span><span class="sxs-lookup"><span data-stu-id="b185c-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="b185c-112">Например все ссылки на объекты, объявленные в стеке, считаются корней сборщиком мусора и будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="b185c-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="b185c-113">Идентификаторы объектов, возвращенных `RootReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов со старых адресов на новые адреса.</span><span class="sxs-lookup"><span data-stu-id="b185c-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="b185c-114">Таким образом, профилировщик должен не пытаться проверять объекты во время `RootReferences` вызова.</span><span class="sxs-lookup"><span data-stu-id="b185c-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="b185c-115">Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) — вызывается, все объекты были перемещены в новые расположения и можно безопасно проверить.</span><span class="sxs-lookup"><span data-stu-id="b185c-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b185c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b185c-116">Requirements</span></span>  
 <span data-ttu-id="b185c-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b185c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b185c-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b185c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b185c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b185c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b185c-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b185c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b185c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b185c-121">See Also</span></span>  
 [<span data-ttu-id="b185c-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b185c-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
