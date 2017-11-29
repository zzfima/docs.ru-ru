---
title: "Метод ICorProfilerCallback5::ConditionalWeakTableElementReferences"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5.ConditionalWeakTableReferences
api_location: Mscorwks.dll
api_type: COM
f1_keywords: CondiitonalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 386cbffea565e6864a77132b96756c073e33fc6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="1d9fc-102">Метод ICorProfilerCallback5::ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="1d9fc-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>
<span data-ttu-id="1d9fc-103">Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-103">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d9fc-104">Syntax</span></span>  
  
```  
HRESULT ConditionalWeakTableElementReferences(     [in]                     ULONG    cRootRefs,     [in, size_is(cRootRefs)] ObjectID keyRefIds[],     [in, size_is(cRootRefs)] ObjectID valueRefIds[],     [in, size_is(cRootRefs)] GCHandleID rootIds[]);};  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d9fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d9fc-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="1d9fc-106">[в] Количество элементов в массивах `keyRefIds`, `valueRefIds` и `rootIds`.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-106">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>  
  
 `keyRefIds`  
 <span data-ttu-id="1d9fc-107">[в] Массив идентификаторов объектов, каждый из которых содержит `ObjectID` для основного элемента в зависимости пары дескриптора.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-107">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>  
  
 `valueRefIds`  
 <span data-ttu-id="1d9fc-108">[в] Массив идентификаторов объектов, каждый из которых содержит `ObjectID` для дополнительного элемента в зависимости пары дескриптора.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-108">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="1d9fc-109">(`keyRefIds[i]` отслеживает `valueRefIds[i]` проверки активности.)</span><span class="sxs-lookup"><span data-stu-id="1d9fc-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>  
  
 `rootIds`  
 <span data-ttu-id="1d9fc-110">[в] Массив значений `GCHandleID`, указывающий на целое число, который содержит дополнительные сведения о корне сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-110">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>  
  
 <span data-ttu-id="1d9fc-111">Ни одно из значений `ObjectID`, возвращаемых методом `ConditionalWeakTableElementReferences` во время обратного вызова самого себя, не является допустимым, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-111">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="1d9fc-112">В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `ConditionalWeakTableElementReferences`.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-112">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="1d9fc-113">Вызов `GarbageCollectionFinished` означает, что все объекты перемещены в новые расположения и можно проводить проверку.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-113">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d9fc-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1d9fc-114">Example</span></span>  
 <span data-ttu-id="1d9fc-115">В следующем примере кода показано, как реализовать [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) и использовать этот метод.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-115">The following code example demonstrates how to implement [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) and use this method.</span></span>  
  
```  
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(  
    ULONG      cRootRefs,  
    ObjectID   keyRefIds[],  
    ObjectID   valueRefIds[],  
    GCHandleID rootIds[])  
{  
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");  
    for (unsigned int i = 0; i < cRootRefs; ++i)  
    {  
        // Save dependency to XML for later retrieval  
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or store dependency to an internal map  
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or add arc to object graph  
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);  
    }  
    return S_OK;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="1d9fc-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d9fc-116">Remarks</span></span>  
 <span data-ttu-id="1d9fc-117">Профилировщик для [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] или более поздних версий реализует [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) интерфейс и записывает зависимости, заданные `ConditionalWeakTableElementReferences` метод.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-117">A profiler for the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] or later versions implements the [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="1d9fc-118">`ICorProfilerCallback5`предоставляет полный набор зависимостей между используемыми объектами, представленного `ConditionalWeakTable` записей.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="1d9fc-119">Эти зависимости и элемента поля, заданные ссылки на [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) позволяют управляемому профилировщику создавать полный граф используемых объектов.</span><span class="sxs-lookup"><span data-stu-id="1d9fc-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9fc-120">Требования</span><span class="sxs-lookup"><span data-stu-id="1d9fc-120">Requirements</span></span>  
 <span data-ttu-id="1d9fc-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d9fc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9fc-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d9fc-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d9fc-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9fc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9fc-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1d9fc-124">See Also</span></span>  
 [<span data-ttu-id="1d9fc-125">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="1d9fc-125">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)
