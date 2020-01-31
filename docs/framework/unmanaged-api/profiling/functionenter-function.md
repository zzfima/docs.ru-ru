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
ms.openlocfilehash: caea1d3d526017c0118f95bb138ee4ac45d2c137
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867000"
---
# <a name="functionenter-function"></a><span data-ttu-id="ff87c-102">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="ff87c-102">FunctionEnter Function</span></span>
<span data-ttu-id="ff87c-103">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="ff87c-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff87c-104">Функция `FunctionEnter` является устаревшей в .NET Framework версии 2,0, и ее использование приведет к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="ff87c-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="ff87c-105">Вместо этого используйте функцию [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ff87c-105">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff87c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff87c-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff87c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff87c-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="ff87c-108">\[в] идентификатор функции, для которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ff87c-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff87c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="ff87c-109">Remarks</span></span>  
 <span data-ttu-id="ff87c-110">Функция `FunctionEnter` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="ff87c-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="ff87c-111">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="ff87c-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ff87c-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="ff87c-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ff87c-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="ff87c-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ff87c-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="ff87c-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ff87c-115">Реализация `FunctionEnter` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ff87c-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ff87c-116">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ff87c-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ff87c-117">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionEnter`.</span><span class="sxs-lookup"><span data-stu-id="ff87c-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="ff87c-118">Кроме того, функция `FunctionEnter` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ff87c-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff87c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ff87c-119">Requirements</span></span>  
 <span data-ttu-id="ff87c-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff87c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff87c-121">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="ff87c-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ff87c-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff87c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff87c-123">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ff87c-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff87c-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff87c-124">See also</span></span>

- [<span data-ttu-id="ff87c-125">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="ff87c-125">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="ff87c-126">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="ff87c-126">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="ff87c-127">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="ff87c-127">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="ff87c-128">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="ff87c-128">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ff87c-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="ff87c-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
