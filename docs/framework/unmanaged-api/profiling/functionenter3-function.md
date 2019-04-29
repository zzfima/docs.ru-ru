---
title: Функция FunctionEnter3
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a731df84af0991f80c560db417df0ffe053a5e2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598939"
---
# <a name="functionenter3-function"></a><span data-ttu-id="34991-102">Функция FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="34991-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="34991-103">Уведомляет профилировщик, что элемент управления передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="34991-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34991-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34991-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34991-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34991-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="34991-106">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="34991-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34991-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="34991-107">Remarks</span></span>  
 <span data-ttu-id="34991-108">`FunctionEnter3` Функцию обратного вызова Уведомляет профилировщик, как функции вызываются, но не поддержки проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="34991-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="34991-109">Используйте [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) для регистрации вашей реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="34991-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="34991-110">`FunctionEnter3` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="34991-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="34991-111">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="34991-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="34991-112">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="34991-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="34991-113">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="34991-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="34991-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="34991-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34991-115">Требования</span><span class="sxs-lookup"><span data-stu-id="34991-115">Requirements</span></span>  
 <span data-ttu-id="34991-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34991-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34991-117">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="34991-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="34991-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34991-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34991-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34991-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34991-120">См. также</span><span class="sxs-lookup"><span data-stu-id="34991-120">See also</span></span>

- [<span data-ttu-id="34991-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="34991-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="34991-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="34991-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="34991-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34991-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="34991-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34991-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="34991-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34991-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="34991-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="34991-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="34991-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="34991-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="34991-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="34991-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="34991-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="34991-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="34991-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="34991-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
