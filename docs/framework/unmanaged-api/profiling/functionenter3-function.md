---
title: "Функция FunctionEnter3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter3
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter3
helpviewer_keywords: FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 08ab1b6adc3d4038a57a187519e96c7a07f1e6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter3-function"></a><span data-ttu-id="fbddd-102">Функция FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="fbddd-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="fbddd-103">Уведомляет профилировщик о передаче управления функции.</span><span class="sxs-lookup"><span data-stu-id="fbddd-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbddd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbddd-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbddd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbddd-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="fbddd-106">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbddd-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbddd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbddd-107">Remarks</span></span>  
 <span data-ttu-id="fbddd-108">`FunctionEnter3` Функция обратного вызова Уведомляет профилировщик, как функции вызываются, но не поддержки проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="fbddd-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="fbddd-109">Используйте [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="fbddd-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="fbddd-110">`FunctionEnter3` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="fbddd-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="fbddd-111">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="fbddd-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="fbddd-112">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="fbddd-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="fbddd-113">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="fbddd-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="fbddd-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="fbddd-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbddd-115">Требования</span><span class="sxs-lookup"><span data-stu-id="fbddd-115">Requirements</span></span>  
 <span data-ttu-id="fbddd-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbddd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbddd-117">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="fbddd-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fbddd-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbddd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbddd-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbddd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbddd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fbddd-120">See Also</span></span>  
 [<span data-ttu-id="fbddd-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="fbddd-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="fbddd-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="fbddd-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="fbddd-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fbddd-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="fbddd-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fbddd-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="fbddd-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fbddd-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="fbddd-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="fbddd-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="fbddd-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="fbddd-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="fbddd-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="fbddd-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="fbddd-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="fbddd-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="fbddd-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="fbddd-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
