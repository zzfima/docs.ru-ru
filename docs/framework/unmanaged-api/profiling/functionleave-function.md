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
ms.openlocfilehash: 774a5d4e48f00ea8c28977f3f685dcd5a8da3199
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440584"
---
# <a name="functionleave-function"></a><span data-ttu-id="f06dd-102">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="f06dd-102">FunctionLeave Function</span></span>
<span data-ttu-id="f06dd-103">Уведомляет профилировщик о том, что функция собирается вернуть вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f06dd-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f06dd-104">Функция `FunctionLeave` является устаревшей в .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f06dd-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="f06dd-105">Он будет продолжать работать, но будет приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="f06dd-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="f06dd-106">Вместо этого используйте функцию [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f06dd-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06dd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f06dd-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f06dd-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="f06dd-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="f06dd-109">окне Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="f06dd-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f06dd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f06dd-110">Remarks</span></span>  
 <span data-ttu-id="f06dd-111">Функция `FunctionLeave` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="f06dd-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="f06dd-112">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="f06dd-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="f06dd-113">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="f06dd-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="f06dd-114">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="f06dd-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="f06dd-115">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="f06dd-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f06dd-116">Реализация `FunctionLeave` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f06dd-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="f06dd-117">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f06dd-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f06dd-118">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave`.</span><span class="sxs-lookup"><span data-stu-id="f06dd-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="f06dd-119">Кроме того, функция `FunctionLeave` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="f06dd-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06dd-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f06dd-120">Requirements</span></span>  
 <span data-ttu-id="f06dd-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f06dd-122">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="f06dd-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f06dd-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f06dd-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f06dd-124">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="f06dd-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06dd-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f06dd-125">See also</span></span>

- [<span data-ttu-id="f06dd-126">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="f06dd-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="f06dd-127">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="f06dd-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="f06dd-128">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="f06dd-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="f06dd-129">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="f06dd-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="f06dd-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="f06dd-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
