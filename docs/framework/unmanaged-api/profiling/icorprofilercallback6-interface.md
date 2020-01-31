---
title: Интерфейс ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864873"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="26726-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="26726-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="26726-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="26726-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="26726-104">Подкласс [ICorProfilerCallback5](icorprofilercallback5-interface.md) , предоставляющий метод обратного вызова, который среда CLR использует для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="26726-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26726-105">Методы</span><span class="sxs-lookup"><span data-stu-id="26726-105">Methods</span></span>  
  
|<span data-ttu-id="26726-106">Метод</span><span class="sxs-lookup"><span data-stu-id="26726-106">Method</span></span>|<span data-ttu-id="26726-107">Описание</span><span class="sxs-lookup"><span data-stu-id="26726-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26726-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="26726-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="26726-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="26726-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26726-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="26726-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26726-111">Требования</span><span class="sxs-lookup"><span data-stu-id="26726-111">Requirements</span></span>  
 <span data-ttu-id="26726-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26726-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26726-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26726-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26726-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26726-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26726-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="26726-115">See also</span></span>

- [<span data-ttu-id="26726-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="26726-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
