---
title: Интерфейс ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452381"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="8a582-102">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="8a582-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="8a582-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="8a582-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="8a582-104">Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемые средой CLR для уведомления профилировщика успешного мусора собираются и впоследствии выгружен динамического метода.</span><span class="sxs-lookup"><span data-stu-id="8a582-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a582-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8a582-105">Methods</span></span>  
  
|<span data-ttu-id="8a582-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8a582-106">Method</span></span>|<span data-ttu-id="8a582-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8a582-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a582-108">Метод DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="8a582-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="8a582-109">Уведомляет профилировщик о динамический метод сборки мусора, которые собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="8a582-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a582-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8a582-110">Requirements</span></span>  
 <span data-ttu-id="8a582-111">**Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a582-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a582-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a582-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="8a582-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a582-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8a582-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8a582-114">See Also</span></span>  
<span data-ttu-id="8a582-115">[Интерфейсы профилирования](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="8a582-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="8a582-116">[Интерфейс ICorProfilerCallback8](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="8a582-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="8a582-117">[Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="8a582-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="8a582-118">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="8a582-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
