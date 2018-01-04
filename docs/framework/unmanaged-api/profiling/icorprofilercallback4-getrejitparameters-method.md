---
title: "Метод ICorProfilerCallback4::GetReJITParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.GetReJITParameters
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e5440fbd016f52642a5626b0cf0b82e7ecea45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="b7868-102">Метод ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="b7868-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="b7868-103">Позволяет задать флаги создания дополнительного кода для нового тела метода перекомпилированной профилировщику кода.</span><span class="sxs-lookup"><span data-stu-id="b7868-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7868-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7868-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7868-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7868-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b7868-106">[in] Модуль, содержащий метод, для которого CLR вызывается с параметрами перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="b7868-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="b7868-107">[in] `MethodDef` Метода, для которого CLR вызывается с параметрами перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="b7868-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="b7868-108">[in] Указатель на [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) интерфейс, который можно использовать профилировщик для предоставления сведений о перекомпиляции JIT-компилятора для метода в процессе повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b7868-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7868-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7868-109">Remarks</span></span>  
 <span data-ttu-id="b7868-110">Проблемы со средой CLR `GetReJITParameters` обратного вызова, чтобы профилировщик может указать параметры для повторной компиляции данного метода.</span><span class="sxs-lookup"><span data-stu-id="b7868-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="b7868-111">`GetReJITParameters` Обратный вызов выполняется только один раз на одну функцию; параметры, предоставленные профилировщику применяются ко всем экземплярам данной функции.</span><span class="sxs-lookup"><span data-stu-id="b7868-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7868-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b7868-112">Requirements</span></span>  
 <span data-ttu-id="b7868-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7868-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7868-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7868-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7868-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7868-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7868-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7868-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7868-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b7868-117">See Also</span></span>  
 [<span data-ttu-id="b7868-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b7868-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b7868-119">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="b7868-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="b7868-120">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="b7868-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="b7868-121">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="b7868-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
