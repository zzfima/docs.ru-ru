---
title: Метод ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca176be93b92e44228d9b4063e87a62263e83e04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184877"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="52805-102">Метод ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="52805-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="52805-103">Позволяет задать флаги создания альтернативного кода для нового тела метода перекомпилированной профилировщику кода.</span><span class="sxs-lookup"><span data-stu-id="52805-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52805-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52805-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52805-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52805-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="52805-106">[in] Модуль, содержащий метод, для которой среда CLR требуются параметры перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="52805-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="52805-107">[in] `MethodDef` Метода, для которой среда CLR требуются параметры перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="52805-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="52805-108">[in] Указатель на [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) интерфейс, который можно использовать профилировщик для предоставления сведений о перекомпиляции JIT для метода в процессе повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="52805-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52805-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="52805-109">Remarks</span></span>  
 <span data-ttu-id="52805-110">Проблемы со средой CLR `GetReJITParameters` обратного вызова, профилировщик можно указать параметры для повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="52805-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="52805-111">`GetReJITParameters` Каждой функцией обратного вызова выдается только один раз; параметрами, предоставленными профилировщик применяются ко всем экземплярам этой функции.</span><span class="sxs-lookup"><span data-stu-id="52805-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52805-112">Требования</span><span class="sxs-lookup"><span data-stu-id="52805-112">Requirements</span></span>  
 <span data-ttu-id="52805-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52805-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52805-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52805-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52805-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52805-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52805-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52805-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52805-117">См. также</span><span class="sxs-lookup"><span data-stu-id="52805-117">See also</span></span>

- [<span data-ttu-id="52805-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="52805-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="52805-119">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="52805-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="52805-120">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="52805-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="52805-121">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="52805-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
