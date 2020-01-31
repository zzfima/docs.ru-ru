---
title: Метод ICorProfilerFunctionControl::SetCodegenFlags
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864678"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="6bc1d-102">Метод ICorProfilerFunctionControl::SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="6bc1d-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="6bc1d-103">Задает один или несколько флагов из перечисления [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) для управления созданием кода для перекомпилированной функции JIT.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bc1d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bc1d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bc1d-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="6bc1d-106">окне Один или несколько флагов из перечисления [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6bc1d-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bc1d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6bc1d-107">Remarks</span></span>  
 <span data-ttu-id="6bc1d-108">Профилировщик получает экземпляр этого интерфейса через обратный вызов [ICorProfilerCallback4:: жетрежитпараметерс](icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6bc1d-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="6bc1d-109">`SetCodegenFlags` позволяет профилировщику управлять созданием кода для повторно скомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="6bc1d-110">Как и в случае с другими параметрами повторной компиляции JIT, флаги создания кода применяются ко всем экземплярам функции.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="6bc1d-111">JIT-компилятор рассматривает эти флаги компиляции вместе с другими флагами, заданными другими источниками, при компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="6bc1d-112">Другие источники включают отладчик, глобальные флаги, заданные профилировщиком при запуске, с помощью метода [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) (со значениями `COR_PRF_DISABLE_INLINING` и `COR_PRF_DISABLE_OPTIMIZATIONS`) и обратного вызова [ICorProfilerCallback:: житинлининг](icorprofilercallback-jitinlining-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="6bc1d-113">JIT-компилятор обеспечивает приоритет к источнику, который запрашивает наименьший уровень оптимизации.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="6bc1d-114">Например, если профилировщик указывает `COR_PRF_DISABLE_INLINING` при запуске, но не указывает `COR_PRF_CODEGEN_DISABLE_INLINING` в обратном вызове [икорпрофилерфунктионконтрол:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) , встраивание по-прежнему отключено.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="6bc1d-115">Аналогично, если профилировщик не задает `COR_PRF_CODEGEN_DISABLE_INLINING` в `SetCodegenFlags`, а затем отключает встраивание с помощью обратного вызова [ICorProfilerCallback:: житинлининг](icorprofilercallback-jitinlining-method.md) , встраивание отключено.</span><span class="sxs-lookup"><span data-stu-id="6bc1d-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc1d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="6bc1d-116">Requirements</span></span>  
 <span data-ttu-id="6bc1d-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc1d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc1d-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6bc1d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6bc1d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bc1d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bc1d-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc1d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc1d-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6bc1d-121">See also</span></span>

- [<span data-ttu-id="6bc1d-122">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="6bc1d-122">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
