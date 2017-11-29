---
title: "Функция FunctionTailcall"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall
helpviewer_keywords: FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8bc0d72ad9c11cb36803cc606b460181b44033f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall-function"></a><span data-ttu-id="97ebe-102">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="97ebe-102">FunctionTailcall Function</span></span>
<span data-ttu-id="97ebe-103">Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.</span><span class="sxs-lookup"><span data-stu-id="97ebe-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97ebe-104">`FunctionTailcall` Функция рекомендуется в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="97ebe-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="97ebe-105">Она будет продолжать работать, но повлечет за собой снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="97ebe-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="97ebe-106">Используйте [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="97ebe-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ebe-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97ebe-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97ebe-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="97ebe-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="97ebe-109">[in] Идентификатор текущей выполняемой функции, внесет с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="97ebe-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97ebe-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="97ebe-110">Remarks</span></span>  
 <span data-ttu-id="97ebe-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и возвратит непосредственно вызывающему объекту функции, сделанные с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="97ebe-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="97ebe-112">Это означает, что [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) не будет выдан обратного вызова для функции, которая является целевой для вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="97ebe-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="97ebe-113">`FunctionTailcall` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="97ebe-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="97ebe-114">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="97ebe-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="97ebe-115">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="97ebe-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="97ebe-116">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="97ebe-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="97ebe-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="97ebe-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="97ebe-118">Реализация `FunctionTailcall` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="97ebe-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="97ebe-119">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="97ebe-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="97ebe-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall` возвращает.</span><span class="sxs-lookup"><span data-stu-id="97ebe-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="97ebe-121">Кроме того `FunctionTailcall` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="97ebe-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ebe-122">Требования</span><span class="sxs-lookup"><span data-stu-id="97ebe-122">Requirements</span></span>  
 <span data-ttu-id="97ebe-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97ebe-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ebe-124">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="97ebe-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="97ebe-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97ebe-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97ebe-126">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="97ebe-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ebe-127">См. также</span><span class="sxs-lookup"><span data-stu-id="97ebe-127">See Also</span></span>  
 [<span data-ttu-id="97ebe-128">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="97ebe-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="97ebe-129">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="97ebe-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="97ebe-130">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="97ebe-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="97ebe-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="97ebe-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
