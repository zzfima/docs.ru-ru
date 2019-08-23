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
ms.openlocfilehash: afc0929b8f1b12f4e0b4551d826b8a1d59990154
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952892"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="ef487-102">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="ef487-102">FunctionTailcall Function</span></span>
<span data-ttu-id="ef487-103">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ef487-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef487-104">`FunctionTailcall` Функция является устаревшей в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="ef487-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ef487-105">Он будет продолжать работать, но будет приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="ef487-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ef487-106">Вместо этого используйте функцию [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ef487-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef487-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef487-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef487-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef487-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ef487-109">окне Идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ef487-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef487-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef487-110">Remarks</span></span>  
 <span data-ttu-id="ef487-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и будет возвращаться непосредственно вызывающему объекту функции, которая выполнила вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ef487-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ef487-112">Это означает, что обратный вызов [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) не будет выдаваться для функции, которая является целевым объектом для вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ef487-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ef487-113">`FunctionTailcall` Функция является обратным вызовом. ее необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="ef487-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="ef487-114">Реализация должна использовать `__declspec`атрибут класса хранения`naked`().</span><span class="sxs-lookup"><span data-stu-id="ef487-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ef487-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="ef487-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ef487-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="ef487-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ef487-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="ef487-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ef487-118">Реализация `FunctionTailcall` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ef487-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ef487-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ef487-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ef487-120">Если выполняется сборка мусора, среда выполнения будет блокироваться до тех пор `FunctionTailcall` , пока не вернет.</span><span class="sxs-lookup"><span data-stu-id="ef487-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="ef487-121">Кроме того, `FunctionTailcall` функция не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ef487-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef487-122">Требования</span><span class="sxs-lookup"><span data-stu-id="ef487-122">Requirements</span></span>  
 <span data-ttu-id="ef487-123">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef487-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef487-124">**Заголовок.** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="ef487-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ef487-125">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="ef487-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef487-126">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ef487-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef487-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ef487-127">See also</span></span>

- [<span data-ttu-id="ef487-128">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="ef487-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ef487-129">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="ef487-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ef487-130">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="ef487-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ef487-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="ef487-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
