---
title: "Интерфейс ICorProfilerCallback6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 733ca2f03e73852f2fef1e42fb9ec961ade2975d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="92d08-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="92d08-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="92d08-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="92d08-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="92d08-104">Подкласс [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , предоставляет метод обратного вызова, который использует общеязыковая среда выполнения для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="92d08-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92d08-105">Методы</span><span class="sxs-lookup"><span data-stu-id="92d08-105">Methods</span></span>  
  
|<span data-ttu-id="92d08-106">Метод</span><span class="sxs-lookup"><span data-stu-id="92d08-106">Method</span></span>|<span data-ttu-id="92d08-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="92d08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92d08-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="92d08-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="92d08-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="92d08-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92d08-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="92d08-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92d08-111">Требования</span><span class="sxs-lookup"><span data-stu-id="92d08-111">Requirements</span></span>  
 <span data-ttu-id="92d08-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92d08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92d08-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92d08-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92d08-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92d08-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d08-115">См. также</span><span class="sxs-lookup"><span data-stu-id="92d08-115">See Also</span></span>  
 [<span data-ttu-id="92d08-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="92d08-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
