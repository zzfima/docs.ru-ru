---
title: "Функция FunctionEnter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0387d6d5eee1c30cb1137072e2c4600f12479e8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter-function"></a><span data-ttu-id="83080-102">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="83080-102">FunctionEnter Function</span></span>
<span data-ttu-id="83080-103">Уведомляет профилировщик о передаче управления функции.</span><span class="sxs-lookup"><span data-stu-id="83080-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83080-104">`FunctionEnter` Функция рекомендуется в .NET Framework версии 2.0 и ее использование повлечет за собой снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="83080-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="83080-105">Используйте [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="83080-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83080-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83080-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83080-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="83080-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="83080-108">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="83080-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83080-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="83080-109">Remarks</span></span>  
 <span data-ttu-id="83080-110">`FunctionEnter` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="83080-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="83080-111">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="83080-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="83080-112">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="83080-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="83080-113">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="83080-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="83080-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="83080-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="83080-115">Реализация `FunctionEnter` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="83080-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="83080-116">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="83080-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="83080-117">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionEnter` возвращает.</span><span class="sxs-lookup"><span data-stu-id="83080-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="83080-118">Кроме того `FunctionEnter` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="83080-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83080-119">Требования</span><span class="sxs-lookup"><span data-stu-id="83080-119">Requirements</span></span>  
 <span data-ttu-id="83080-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83080-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83080-121">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="83080-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="83080-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83080-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83080-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="83080-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83080-124">См. также</span><span class="sxs-lookup"><span data-stu-id="83080-124">See Also</span></span>  
 [<span data-ttu-id="83080-125">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="83080-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="83080-126">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="83080-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="83080-127">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="83080-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="83080-128">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="83080-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="83080-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="83080-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
