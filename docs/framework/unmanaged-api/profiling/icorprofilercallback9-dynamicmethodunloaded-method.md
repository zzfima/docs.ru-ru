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
ms.openlocfilehash: 27e68c82a04b78a18f51f0a2c9ec712036521368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513546"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="bbb2a-102">Метод ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="bbb2a-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="bbb2a-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="bbb2a-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="bbb2a-104">Уведомляет профилировщик, каждый раз, когда динамический метод является мусором собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="bbb2a-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbb2a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbb2a-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbb2a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bbb2a-106">Parameters</span></span>  
<span data-ttu-id="bbb2a-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="bbb2a-107">[in] `functionId`</span></span>  
<span data-ttu-id="bbb2a-108">Идентификатор функции в памяти, был удален мусора собираются и выгрузки.</span><span class="sxs-lookup"><span data-stu-id="bbb2a-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="bbb2a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bbb2a-109">Requirements</span></span>  
 <span data-ttu-id="bbb2a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbb2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbb2a-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbb2a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbb2a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbb2a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbb2a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bbb2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb2a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb2a-114">See also</span></span>
- [<span data-ttu-id="bbb2a-115">Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="bbb2a-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="bbb2a-116">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="bbb2a-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="bbb2a-117">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="bbb2a-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="bbb2a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="bbb2a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
