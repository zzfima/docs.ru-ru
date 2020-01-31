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
ms.openlocfilehash: bd03eccc923049c4a49062d18bd11659f3316e8a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866827"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="0e845-102">Функция FunctionTailcall</span><span class="sxs-lookup"><span data-stu-id="0e845-102">FunctionTailcall Function</span></span>
<span data-ttu-id="0e845-103">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="0e845-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e845-104">Функция `FunctionTailcall` устарела в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="0e845-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0e845-105">Он будет продолжать работать, но будет приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="0e845-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="0e845-106">Вместо этого используйте функцию [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0e845-106">Use the [FunctionTailcall2](functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e845-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e845-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e845-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e845-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="0e845-109">\[в] идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="0e845-109">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e845-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="0e845-110">Remarks</span></span>  
 <span data-ttu-id="0e845-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и будет возвращаться непосредственно вызывающему объекту функции, которая выполнила вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="0e845-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="0e845-112">Это означает, что обратный вызов [FunctionLeave](functionleave-function.md) не будет выдаваться для функции, которая является целевым объектом для вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="0e845-112">This means that a [FunctionLeave](functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="0e845-113">Функция `FunctionTailcall` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="0e845-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="0e845-114">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="0e845-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="0e845-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="0e845-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="0e845-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="0e845-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="0e845-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="0e845-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0e845-118">Реализация `FunctionTailcall` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0e845-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="0e845-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0e845-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0e845-120">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionTailcall`.</span><span class="sxs-lookup"><span data-stu-id="0e845-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="0e845-121">Кроме того, функция `FunctionTailcall` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="0e845-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e845-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0e845-122">Requirements</span></span>  
 <span data-ttu-id="0e845-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e845-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e845-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="0e845-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0e845-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e845-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e845-126">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="0e845-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e845-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e845-127">See also</span></span>

- [<span data-ttu-id="0e845-128">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="0e845-128">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="0e845-129">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="0e845-129">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="0e845-130">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="0e845-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="0e845-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="0e845-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
