---
title: "Метод ICorProfilerFunctionControl::SetCodegenFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetCodegenFlags
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9264e717da62c88b6f2f6eca262b5635fc928741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="a0074-102">Метод ICorProfilerFunctionControl::SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="a0074-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="a0074-103">Задает один или несколько флагов из [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) перечисления с целью управления генерацией кода для just-in-time (JIT) перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="a0074-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0074-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0074-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0074-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0074-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="a0074-106">[in] Один или несколько флагов из [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="a0074-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0074-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0074-107">Remarks</span></span>  
 <span data-ttu-id="a0074-108">Профилировщик получает экземпляр этого интерфейса через [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a0074-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="a0074-109">`SetCodegenFlags`позволяет профилировщику контроля генерации кода для перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="a0074-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="a0074-110">Как и все другие JIT перекомпиляции параметры, флаги создания кода применяются ко всем экземплярам функции.</span><span class="sxs-lookup"><span data-stu-id="a0074-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="a0074-111">JIT-компилятор рассматривает эти флаги компиляции, а также другие флаги, заданные для других источников, при компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="a0074-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="a0074-112">Другие источники включают отладчик, глобальные флаги задано с помощью профилировщика при запуске с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод (со значениями `COR_PRF_DISABLE_INLINING` и `COR_PRF_DISABLE_OPTIMIZATIONS`) и профилировщика [ ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a0074-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="a0074-113">JIT-компилятор предоставляет приоритет для источника, который требует наименьшего объема оптимизации.</span><span class="sxs-lookup"><span data-stu-id="a0074-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="a0074-114">Например, если профилировщик указывает `COR_PRF_DISABLE_INLINING` во время запуска, но не указывает `COR_PRF_CODEGEN_DISABLE_INLINING` в [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) обратного вызова, встраивание по-прежнему отключен.</span><span class="sxs-lookup"><span data-stu-id="a0074-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="a0074-115">Аналогичным образом Если профилировщик указывает `COR_PRF_CODEGEN_DISABLE_INLINING` в `SetCodegenFlags`, но затем отключает встраивание с помощью [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) обратного вызова, встраивание отключена.</span><span class="sxs-lookup"><span data-stu-id="a0074-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0074-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a0074-116">Requirements</span></span>  
 <span data-ttu-id="a0074-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0074-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0074-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0074-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0074-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0074-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0074-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0074-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0074-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a0074-121">See Also</span></span>  
 [<span data-ttu-id="a0074-122">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="a0074-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
