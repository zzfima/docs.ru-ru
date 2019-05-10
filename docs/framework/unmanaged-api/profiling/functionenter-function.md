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
ms.openlocfilehash: 9d38c32c4ed938de4a517009c5a76310df6d39fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586755"
---
# <a name="functionenter-function"></a><span data-ttu-id="af655-102">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="af655-102">FunctionEnter Function</span></span>
<span data-ttu-id="af655-103">Уведомляет профилировщик, что элемент управления передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="af655-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af655-104">`FunctionEnter` Функция является устаревшим в .NET Framework версии 2.0, и его использование будет привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="af655-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="af655-105">Используйте [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="af655-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af655-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af655-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af655-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="af655-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="af655-108">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af655-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af655-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="af655-109">Remarks</span></span>  
 <span data-ttu-id="af655-110">`FunctionEnter` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="af655-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="af655-111">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="af655-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="af655-112">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="af655-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="af655-113">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="af655-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="af655-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="af655-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="af655-115">Реализация `FunctionEnter` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="af655-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="af655-116">Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="af655-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="af655-117">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionEnter` возвращает.</span><span class="sxs-lookup"><span data-stu-id="af655-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="af655-118">Кроме того `FunctionEnter` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="af655-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af655-119">Требования</span><span class="sxs-lookup"><span data-stu-id="af655-119">Requirements</span></span>  
 <span data-ttu-id="af655-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af655-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af655-121">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="af655-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="af655-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af655-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af655-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="af655-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af655-124">См. также</span><span class="sxs-lookup"><span data-stu-id="af655-124">See also</span></span>

- [<span data-ttu-id="af655-125">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="af655-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="af655-126">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="af655-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="af655-127">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="af655-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="af655-128">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="af655-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="af655-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="af655-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
