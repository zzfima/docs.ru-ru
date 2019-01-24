---
title: Функция FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f01117d52ba49012120546db5095ccad8baa6e73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531627"
---
# <a name="functionenter2-function"></a><span data-ttu-id="2ccde-102">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="2ccde-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="2ccde-103">Уведомляет профилировщик о том, что элемент управления передается в функцию и предоставляет информацию о стеке кадра и аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="2ccde-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="2ccde-104">Эта функция заменяет [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="2ccde-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ccde-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ccde-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ccde-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ccde-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="2ccde-107">[in] Идентификатор функции, в которую передается элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2ccde-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="2ccde-108">[in] Функция пересопоставленный идентификатора, который ранее указано профилировщик с помощью [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="2ccde-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="2ccde-109">[in] Объект `COR_PRF_FRAME_INFO` значение, которое указывает на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="2ccde-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="2ccde-110">Профилировщик должен интерпретировать его как непрозрачный дескриптор, который может быть передан в модуль выполнения в [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2ccde-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="2ccde-111">[in] Указатель на [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) структура, которая определяет расположения в памяти из аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="2ccde-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="2ccde-112">Чтобы получить доступ к информации аргумент `COR_PRF_ENABLE_FUNCTION_ARGS` должен быть установлен флаг.</span><span class="sxs-lookup"><span data-stu-id="2ccde-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="2ccde-113">Можно использовать профилировщик [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод, чтобы задать флаги событий.</span><span class="sxs-lookup"><span data-stu-id="2ccde-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ccde-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ccde-114">Remarks</span></span>  
 <span data-ttu-id="2ccde-115">Значения `func` и `argumentInfo` параметров не являются действительными после `FunctionEnter2` функция возвращает потому, что значения, могут быть изменены или удалены.</span><span class="sxs-lookup"><span data-stu-id="2ccde-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="2ccde-116">`FunctionEnter2` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="2ccde-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="2ccde-117">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="2ccde-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2ccde-118">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="2ccde-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="2ccde-119">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="2ccde-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="2ccde-120">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="2ccde-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2ccde-121">Реализация `FunctionEnter2` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2ccde-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2ccde-122">Реализация не должны сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2ccde-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2ccde-123">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionEnter2` возвращает.</span><span class="sxs-lookup"><span data-stu-id="2ccde-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="2ccde-124">Кроме того `FunctionEnter2` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="2ccde-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ccde-125">Требования</span><span class="sxs-lookup"><span data-stu-id="2ccde-125">Requirements</span></span>  
 <span data-ttu-id="2ccde-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ccde-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccde-127">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2ccde-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2ccde-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ccde-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ccde-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccde-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccde-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2ccde-130">See also</span></span>
- [<span data-ttu-id="2ccde-131">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="2ccde-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="2ccde-132">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="2ccde-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="2ccde-133">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="2ccde-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2ccde-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="2ccde-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
