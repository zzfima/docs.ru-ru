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
ms.openlocfilehash: a6c480af921fb0259ef85beec8d8f65bdd430522
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689322"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="2cf2c-102">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="2cf2c-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="2cf2c-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="2cf2c-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="2cf2c-104">Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, среда CLR, используемый для уведомления профилировщика успешного мусора собираются и впоследствии выгружен динамического метода.</span><span class="sxs-lookup"><span data-stu-id="2cf2c-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cf2c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2cf2c-105">Methods</span></span>  
  
|<span data-ttu-id="2cf2c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2cf2c-106">Method</span></span>|<span data-ttu-id="2cf2c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="2cf2c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cf2c-108">Метод DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="2cf2c-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="2cf2c-109">Уведомляет профилировщик о динамический метод сборки мусора, которые собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="2cf2c-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cf2c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2cf2c-110">Requirements</span></span>  
 <span data-ttu-id="2cf2c-111">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf2c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf2c-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cf2c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="2cf2c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2cf2c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2cf2c-114">See also</span></span>
- [<span data-ttu-id="2cf2c-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="2cf2c-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2cf2c-116">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="2cf2c-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="2cf2c-117">Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="2cf2c-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="2cf2c-118">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="2cf2c-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
