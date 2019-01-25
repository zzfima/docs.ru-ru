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
ms.openlocfilehash: a38d4858d248ef4eefbcb9d97c13e68d9507fb12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665036"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="ecaec-102">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="ecaec-102">FunctionTailcall Function</span></span>
<span data-ttu-id="ecaec-103">Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.</span><span class="sxs-lookup"><span data-stu-id="ecaec-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecaec-104">`FunctionTailcall` Рекомендуется использовать функцию в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="ecaec-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ecaec-105">Она будет продолжать работать, но будет привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="ecaec-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ecaec-106">Используйте [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="ecaec-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecaec-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecaec-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecaec-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecaec-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ecaec-109">[in] Идентификатор текущей выполняемой функции, который собираетесь сделать с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ecaec-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecaec-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecaec-110">Remarks</span></span>  
 <span data-ttu-id="ecaec-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и возвращает непосредственно вызывающему объекту функции, внесенные с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ecaec-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ecaec-112">Это означает, что [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) обратного вызова не выдается для функции, которая является целевым объектом вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ecaec-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ecaec-113">`FunctionTailcall` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="ecaec-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="ecaec-114">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="ecaec-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ecaec-115">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="ecaec-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ecaec-116">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="ecaec-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ecaec-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="ecaec-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ecaec-118">Реализация `FunctionTailcall` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ecaec-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ecaec-119">Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ecaec-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ecaec-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall` возвращает.</span><span class="sxs-lookup"><span data-stu-id="ecaec-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="ecaec-121">Кроме того `FunctionTailcall` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="ecaec-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecaec-122">Требования</span><span class="sxs-lookup"><span data-stu-id="ecaec-122">Requirements</span></span>  
 <span data-ttu-id="ecaec-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecaec-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecaec-124">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ecaec-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ecaec-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecaec-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecaec-126">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ecaec-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaec-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ecaec-127">See also</span></span>
- [<span data-ttu-id="ecaec-128">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="ecaec-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ecaec-129">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="ecaec-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ecaec-130">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="ecaec-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ecaec-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="ecaec-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
