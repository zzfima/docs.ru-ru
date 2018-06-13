---
title: Интерфейс ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455287"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="0d8c6-102">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="0d8c6-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="0d8c6-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="0d8c6-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="0d8c6-104">Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, используемые средой CLR для уведомления профилировщика, запуска и завершения JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="0d8c6-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="0d8c6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0d8c6-105">Methods</span></span>  
  
|<span data-ttu-id="0d8c6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0d8c6-106">Method</span></span>|<span data-ttu-id="0d8c6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0d8c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d8c6-108">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="0d8c6-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="0d8c6-109">Уведомляет профилировщик о начале JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="0d8c6-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="0d8c6-110">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="0d8c6-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="0d8c6-111">Уведомляет профилировщик об окончании JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="0d8c6-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d8c6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0d8c6-112">Requirements</span></span>  
 <span data-ttu-id="0d8c6-113">**Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d8c6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d8c6-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d8c6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="0d8c6-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d8c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0d8c6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0d8c6-116">See Also</span></span>  
<span data-ttu-id="0d8c6-117">[Интерфейсы профилирования](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="0d8c6-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="0d8c6-118">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="0d8c6-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
