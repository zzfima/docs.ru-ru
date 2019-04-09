---
title: Метод ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b616017745d7cc33d57b1626b6c27c59a0a60a32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091178"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="7ba47-102">Метод ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="7ba47-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="7ba47-103">Уведомляет профилировщик о корневыми ссылками после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7ba47-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ba47-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ba47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ba47-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="7ba47-106">[in] Число ссылок в `rootRefIds` массива.</span><span class="sxs-lookup"><span data-stu-id="7ba47-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="7ba47-107">[in] Массив идентификаторов объектов, которые ссылаются на статический объект или объект в стеке.</span><span class="sxs-lookup"><span data-stu-id="7ba47-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ba47-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ba47-108">Remarks</span></span>  
 <span data-ttu-id="7ba47-109">Оба `RootReferences` и [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) вызываемые для уведомления профилировщика.</span><span class="sxs-lookup"><span data-stu-id="7ba47-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="7ba47-110">Обычно профилировщик реализует одно из них, но не оба одновременно, так как данные, передаваемые `RootReferences2` является надмножеством информации, переданной в `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="7ba47-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="7ba47-111">Существует возможность `rootRefIds` массив должен содержать пустой объект.</span><span class="sxs-lookup"><span data-stu-id="7ba47-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="7ba47-112">Например все ссылки на объекты, объявленные в стеке, рассматриваются как корни сборщиком мусора и всегда будет считаться.</span><span class="sxs-lookup"><span data-stu-id="7ba47-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="7ba47-113">Идентификаторы объектов, возвращенных `RootReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старого адреса в новые адреса.</span><span class="sxs-lookup"><span data-stu-id="7ba47-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="7ba47-114">Таким образом, профилировщики не должны пытаться проверять объекты во время `RootReferences` вызова.</span><span class="sxs-lookup"><span data-stu-id="7ba47-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="7ba47-115">Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) является именем, все объекты были перемещены в новые расположения и можно безопасно проверить.</span><span class="sxs-lookup"><span data-stu-id="7ba47-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ba47-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7ba47-116">Requirements</span></span>  
 <span data-ttu-id="7ba47-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ba47-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ba47-118">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ba47-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ba47-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ba47-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7ba47-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7ba47-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ba47-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7ba47-121">See also</span></span>

- [<span data-ttu-id="7ba47-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7ba47-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
