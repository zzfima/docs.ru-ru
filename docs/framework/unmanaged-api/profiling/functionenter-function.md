---
title: Функция FunctionEnter
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6018b5b06a138b38b7b97df280a3e4c4ea0512d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208414"
---
# <a name="functionenter-function"></a><span data-ttu-id="8351e-102">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="8351e-102">FunctionEnter Function</span></span>
<span data-ttu-id="8351e-103">Уведомляет профилировщик, что элемент управления передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="8351e-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8351e-104">`FunctionEnter` Функция является устаревшим в .NET Framework версии 2.0, и его использование будет привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="8351e-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="8351e-105">Используйте [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="8351e-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8351e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8351e-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8351e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8351e-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="8351e-108">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8351e-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8351e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8351e-109">Remarks</span></span>  
 <span data-ttu-id="8351e-110">`FunctionEnter` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="8351e-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="8351e-111">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="8351e-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="8351e-112">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="8351e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="8351e-113">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="8351e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="8351e-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="8351e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8351e-115">Реализация `FunctionEnter` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8351e-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="8351e-116">Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8351e-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8351e-117">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionEnter` возвращает.</span><span class="sxs-lookup"><span data-stu-id="8351e-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="8351e-118">Кроме того `FunctionEnter` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="8351e-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8351e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8351e-119">Requirements</span></span>  
 <span data-ttu-id="8351e-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8351e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8351e-121">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8351e-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8351e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8351e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8351e-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="8351e-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8351e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8351e-124">See also</span></span>

- [<span data-ttu-id="8351e-125">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="8351e-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="8351e-126">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="8351e-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="8351e-127">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="8351e-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="8351e-128">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="8351e-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="8351e-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="8351e-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
