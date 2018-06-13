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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2614ad988496a22f0e6234c2f3300e22ef548308
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452446"
---
# <a name="functionleave-function"></a><span data-ttu-id="61888-102">Функция FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="61888-102">FunctionLeave Function</span></span>
<span data-ttu-id="61888-103">Уведомляет профилировщик, что функция будет возвращать вызывающему.</span><span class="sxs-lookup"><span data-stu-id="61888-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61888-104">`FunctionLeave` Функция рекомендуется в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="61888-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="61888-105">Она будет продолжать работать, но повлечет за собой снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="61888-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="61888-106">Используйте [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="61888-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61888-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61888-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61888-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="61888-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="61888-109">[in] Идентификатор функции, которая возвращает.</span><span class="sxs-lookup"><span data-stu-id="61888-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61888-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="61888-110">Remarks</span></span>  
 <span data-ttu-id="61888-111">`FunctionLeave` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="61888-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="61888-112">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="61888-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="61888-113">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="61888-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="61888-114">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="61888-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="61888-115">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="61888-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="61888-116">Реализация `FunctionLeave` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="61888-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="61888-117">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="61888-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="61888-118">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave` возвращает.</span><span class="sxs-lookup"><span data-stu-id="61888-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="61888-119">Кроме того `FunctionLeave` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="61888-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61888-120">Требования</span><span class="sxs-lookup"><span data-stu-id="61888-120">Requirements</span></span>  
 <span data-ttu-id="61888-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61888-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61888-122">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="61888-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="61888-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61888-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61888-124">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="61888-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61888-125">См. также</span><span class="sxs-lookup"><span data-stu-id="61888-125">See Also</span></span>  
 [<span data-ttu-id="61888-126">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="61888-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="61888-127">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="61888-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="61888-128">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="61888-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="61888-129">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="61888-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="61888-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="61888-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
