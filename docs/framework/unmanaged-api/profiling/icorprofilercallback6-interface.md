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
ms.openlocfilehash: dca83aca3aee4a072e90793e1bb33526b6e5ebd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="81150-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="81150-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="81150-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="81150-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="81150-104">Подкласс [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , предоставляет метод обратного вызова, который использует общеязыковая среда выполнения для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="81150-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81150-105">Методы</span><span class="sxs-lookup"><span data-stu-id="81150-105">Methods</span></span>  
  
|<span data-ttu-id="81150-106">Метод</span><span class="sxs-lookup"><span data-stu-id="81150-106">Method</span></span>|<span data-ttu-id="81150-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81150-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81150-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="81150-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="81150-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="81150-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81150-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="81150-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81150-111">Требования</span><span class="sxs-lookup"><span data-stu-id="81150-111">Requirements</span></span>  
 <span data-ttu-id="81150-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81150-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81150-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81150-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81150-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81150-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81150-115">См. также</span><span class="sxs-lookup"><span data-stu-id="81150-115">See Also</span></span>  
 [<span data-ttu-id="81150-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="81150-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
