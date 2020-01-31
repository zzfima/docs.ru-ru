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
ms.openlocfilehash: 948628f469eecabfbbe792dcc3edf2e1204ffc36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865965"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="681a4-102">Метод ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="681a4-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="681a4-103">Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="681a4-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="681a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="681a4-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="681a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="681a4-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="681a4-106">окне Число ссылок в массиве `rootRefIds`.</span><span class="sxs-lookup"><span data-stu-id="681a4-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="681a4-107">окне Массив идентификаторов объектов, ссылающихся либо на статический объект, либо на объект в стеке.</span><span class="sxs-lookup"><span data-stu-id="681a4-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="681a4-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="681a4-108">Remarks</span></span>  
 <span data-ttu-id="681a4-109">Для уведомления профилировщика вызываются `RootReferences` и [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="681a4-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="681a4-110">Как правило, профилировщики реализуют один или другой, но не оба, так как сведения, передаваемые в `RootReferences2`, являются надмножеством, передаваемыми `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="681a4-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="681a4-111">Массив `rootRefIds` может содержать объект null.</span><span class="sxs-lookup"><span data-stu-id="681a4-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="681a4-112">Например, все ссылки на объекты, объявленные в стеке, рассматриваются сборщиком мусора как корни и всегда будут сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="681a4-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="681a4-113">Идентификаторы объектов, возвращаемые `RootReferences`, недопустимы в самом обратном вызове, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса.</span><span class="sxs-lookup"><span data-stu-id="681a4-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="681a4-114">Таким образом, профилировщики не должны пытаться проверять объекты во время вызова `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="681a4-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="681a4-115">При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.</span><span class="sxs-lookup"><span data-stu-id="681a4-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="681a4-116">Требования</span><span class="sxs-lookup"><span data-stu-id="681a4-116">Requirements</span></span>  
 <span data-ttu-id="681a4-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="681a4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="681a4-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="681a4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="681a4-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="681a4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="681a4-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="681a4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681a4-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="681a4-121">See also</span></span>

- [<span data-ttu-id="681a4-122">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="681a4-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
