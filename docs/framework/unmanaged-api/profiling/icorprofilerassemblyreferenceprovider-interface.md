---
title: "Интерфейс ICorProfilerAssemblyReferenceProvider"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerAssemblyReferenceProvider
api_location: mscorwks.dll
api_type: COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2120e400d4ecd23c86cdae7b12d8706b35e8ca08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="89954-102">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="89954-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="89954-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="89954-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="89954-104">Позволяет профилировщику сообщать среде (CLR) из ссылок на сборки, которые профилировщик добавит в [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="89954-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89954-105">Методы</span><span class="sxs-lookup"><span data-stu-id="89954-105">Methods</span></span>  
  
|<span data-ttu-id="89954-106">Метод</span><span class="sxs-lookup"><span data-stu-id="89954-106">Method</span></span>|<span data-ttu-id="89954-107">Описание</span><span class="sxs-lookup"><span data-stu-id="89954-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89954-108">Метод AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="89954-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="89954-109">Информирует среду CLR о ссылке на сборку, которую профилировщик планирует добавить в [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="89954-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89954-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="89954-110">Remarks</span></span>  
 <span data-ttu-id="89954-111">Среда CLR передает профилировщику `ICorProfilerAssemblyReferenceProvider` объект интерфейса в [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="89954-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="89954-112">Это позволяет профилировщику информировать среду CLR ссылки на сборки, которые профилировщик планирует добавить в дальнейшем [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="89954-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="89954-113">callback.</span><span class="sxs-lookup"><span data-stu-id="89954-113">callback.</span></span> <span data-ttu-id="89954-114">В результате повышается точность обхода замыкания ссылки на сборку среды CLR и его алгоритмов, определяющих возможность совместного доступа к сборкам.</span><span class="sxs-lookup"><span data-stu-id="89954-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="89954-115">Этот интерфейс может использоваться только в [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратный вызов, который передает этот объект интерфейса в профилировщик.</span><span class="sxs-lookup"><span data-stu-id="89954-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89954-116">Требования</span><span class="sxs-lookup"><span data-stu-id="89954-116">Requirements</span></span>  
 <span data-ttu-id="89954-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89954-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89954-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89954-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89954-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89954-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89954-120">См. также</span><span class="sxs-lookup"><span data-stu-id="89954-120">See Also</span></span>  
 [<span data-ttu-id="89954-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="89954-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
