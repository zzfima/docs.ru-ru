---
title: "Функция FunctionLeave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave
helpviewer_keywords: FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3368a97adf6ffceaa5ac56b7ffe16d6e2802437c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave-function"></a><span data-ttu-id="2578c-102">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="2578c-102">FunctionLeave Function</span></span>
<span data-ttu-id="2578c-103">Уведомляет профилировщик, что функция будет возвращать вызывающему.</span><span class="sxs-lookup"><span data-stu-id="2578c-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2578c-104">`FunctionLeave` Функция рекомендуется в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="2578c-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="2578c-105">Она будет продолжать работать, но повлечет за собой снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="2578c-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="2578c-106">Используйте [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="2578c-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2578c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2578c-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2578c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2578c-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="2578c-109">[in] Идентификатор функции, которая возвращает.</span><span class="sxs-lookup"><span data-stu-id="2578c-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2578c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2578c-110">Remarks</span></span>  
 <span data-ttu-id="2578c-111">`FunctionLeave` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="2578c-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="2578c-112">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="2578c-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2578c-113">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="2578c-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="2578c-114">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="2578c-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="2578c-115">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="2578c-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2578c-116">Реализация `FunctionLeave` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2578c-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2578c-117">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="2578c-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2578c-118">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave` возвращает.</span><span class="sxs-lookup"><span data-stu-id="2578c-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="2578c-119">Кроме того `FunctionLeave` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="2578c-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2578c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2578c-120">Requirements</span></span>  
 <span data-ttu-id="2578c-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2578c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2578c-122">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2578c-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2578c-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2578c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2578c-124">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="2578c-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2578c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2578c-125">See Also</span></span>  
 [<span data-ttu-id="2578c-126">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="2578c-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="2578c-127">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="2578c-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="2578c-128">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="2578c-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="2578c-129">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="2578c-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="2578c-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="2578c-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
