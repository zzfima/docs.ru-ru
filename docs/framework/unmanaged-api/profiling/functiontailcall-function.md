---
title: Функция FunctionTailcall
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 656f2498c7dd9ba165ab6759d8ca3b26e0d7c93f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207049"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="ba9f9-102">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="ba9f9-102">FunctionTailcall Function</span></span>
<span data-ttu-id="ba9f9-103">Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba9f9-104">`FunctionTailcall` Рекомендуется использовать функцию в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ba9f9-105">Она будет продолжать работать, но будет привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ba9f9-106">Используйте [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9f9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba9f9-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba9f9-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba9f9-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ba9f9-109">[in] Идентификатор текущей выполняемой функции, который собираетесь сделать с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba9f9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba9f9-110">Remarks</span></span>  
 <span data-ttu-id="ba9f9-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и возвращает непосредственно вызывающему объекту функции, внесенные с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ba9f9-112">Это означает, что [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) обратного вызова не выдается для функции, которая является целевым объектом вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ba9f9-113">`FunctionTailcall` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="ba9f9-114">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ba9f9-115">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ba9f9-116">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="ba9f9-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ba9f9-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ba9f9-118">Реализация `FunctionTailcall` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ba9f9-119">Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ba9f9-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall` возвращает.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="ba9f9-121">Кроме того `FunctionTailcall` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="ba9f9-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba9f9-122">Требования</span><span class="sxs-lookup"><span data-stu-id="ba9f9-122">Requirements</span></span>  
 <span data-ttu-id="ba9f9-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba9f9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba9f9-124">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ba9f9-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ba9f9-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba9f9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba9f9-126">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ba9f9-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9f9-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ba9f9-127">See also</span></span>

- [<span data-ttu-id="ba9f9-128">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="ba9f9-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ba9f9-129">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="ba9f9-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ba9f9-130">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="ba9f9-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ba9f9-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="ba9f9-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
