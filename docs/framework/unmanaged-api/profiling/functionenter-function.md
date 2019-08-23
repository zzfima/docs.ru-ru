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
ms.openlocfilehash: 354736890a4b042a8da5e747a0ab6ea3777e398e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952900"
---
# <a name="functionenter-function"></a><span data-ttu-id="50793-102">Функция FunctionEnter</span><span class="sxs-lookup"><span data-stu-id="50793-102">FunctionEnter Function</span></span>
<span data-ttu-id="50793-103">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="50793-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50793-104">`FunctionEnter` Функция является устаревшей в .NET Framework версии 2,0, и ее использование приведет к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="50793-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="50793-105">Вместо этого используйте функцию [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="50793-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50793-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50793-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50793-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="50793-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="50793-108">окне Идентификатор функции, которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="50793-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50793-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="50793-109">Remarks</span></span>  
 <span data-ttu-id="50793-110">`FunctionEnter` Функция является обратным вызовом. ее необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="50793-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="50793-111">Реализация должна использовать `__declspec`атрибут класса хранения`naked`().</span><span class="sxs-lookup"><span data-stu-id="50793-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="50793-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="50793-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="50793-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="50793-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="50793-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="50793-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="50793-115">Реализация `FunctionEnter` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="50793-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="50793-116">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="50793-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="50793-117">Если выполняется сборка мусора, среда выполнения будет блокироваться до тех пор `FunctionEnter` , пока не вернет.</span><span class="sxs-lookup"><span data-stu-id="50793-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="50793-118">Кроме того, `FunctionEnter` функция не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="50793-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50793-119">Требования</span><span class="sxs-lookup"><span data-stu-id="50793-119">Requirements</span></span>  
 <span data-ttu-id="50793-120">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50793-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50793-121">**Заголовок.** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="50793-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="50793-122">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="50793-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50793-123">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="50793-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50793-124">См. также</span><span class="sxs-lookup"><span data-stu-id="50793-124">See also</span></span>

- [<span data-ttu-id="50793-125">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="50793-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="50793-126">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="50793-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="50793-127">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="50793-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="50793-128">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="50793-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="50793-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="50793-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
