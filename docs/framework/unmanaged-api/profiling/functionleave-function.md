---
title: Функция FunctionLeave
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: a9ab8c81c995bbec41db217c904e03dd70351aee
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866888"
---
# <a name="functionleave-function"></a><span data-ttu-id="2750c-102">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="2750c-102">FunctionLeave Function</span></span>
<span data-ttu-id="2750c-103">Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="2750c-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2750c-104">Функция `FunctionLeave` является устаревшей в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="2750c-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="2750c-105">Он будет продолжать работать, но будет приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="2750c-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="2750c-106">Вместо этого используйте функцию [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="2750c-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2750c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2750c-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2750c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2750c-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="2750c-109">\[in] Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="2750c-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="2750c-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2750c-110">Remarks</span></span>  
 <span data-ttu-id="2750c-111">Функция `FunctionLeave` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="2750c-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="2750c-112">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="2750c-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2750c-113">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="2750c-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="2750c-114">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="2750c-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="2750c-115">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="2750c-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2750c-116">Реализация `FunctionLeave` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2750c-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2750c-117">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2750c-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2750c-118">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave`.</span><span class="sxs-lookup"><span data-stu-id="2750c-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="2750c-119">Кроме того, функция `FunctionLeave` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="2750c-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2750c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2750c-120">Requirements</span></span>  
 <span data-ttu-id="2750c-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2750c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2750c-122">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="2750c-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2750c-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2750c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2750c-124">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="2750c-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2750c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="2750c-125">See also</span></span>

- [<span data-ttu-id="2750c-126">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="2750c-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="2750c-127">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="2750c-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="2750c-128">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="2750c-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="2750c-129">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="2750c-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2750c-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="2750c-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
