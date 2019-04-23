---
title: Метод ICorProfilerCallback9::DynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211014"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="33f32-102">Метод ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="33f32-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="33f32-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="33f32-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="33f32-104">Уведомляет профилировщик, каждый раз, когда динамический метод является мусором собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="33f32-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f32-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33f32-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33f32-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="33f32-106">Parameters</span></span>  
<span data-ttu-id="33f32-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="33f32-107">[in] `functionId`</span></span>  
<span data-ttu-id="33f32-108">Идентификатор функции в памяти, был удален мусора собираются и выгрузки.</span><span class="sxs-lookup"><span data-stu-id="33f32-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="33f32-109">Требования</span><span class="sxs-lookup"><span data-stu-id="33f32-109">Requirements</span></span>  
 <span data-ttu-id="33f32-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33f32-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33f32-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33f32-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33f32-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33f32-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33f32-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33f32-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f32-114">См. также</span><span class="sxs-lookup"><span data-stu-id="33f32-114">See also</span></span>

- [<span data-ttu-id="33f32-115">Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="33f32-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="33f32-116">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="33f32-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="33f32-117">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="33f32-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="33f32-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="33f32-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
