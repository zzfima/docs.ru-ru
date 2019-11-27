---
title: Функция FunctionTailcall2
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: db3c3d38e0200f9849c84d7605a436816d56b813
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427424"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="fae27-102">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="fae27-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="fae27-103">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail и предоставляет сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="fae27-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fae27-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fae27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fae27-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="fae27-106">окне Идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="fae27-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="fae27-107">окне Идентификатор повторно сопоставленной функции, который ранее был указан с помощью [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), для выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="fae27-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="fae27-108">окне Значение `COR_PRF_FRAME_INFO`, указывающее на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="fae27-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="fae27-109">Профилировщик должен рассматривать это как непрозрачный маркер, который можно передать обратно в подсистему выполнения метода [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fae27-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fae27-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="fae27-110">Remarks</span></span>  
 <span data-ttu-id="fae27-111">Целевая функция вызова с префиксом tail будет использовать текущий кадр стека и будет возвращаться непосредственно вызывающему объекту функции, которая выполнила вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="fae27-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="fae27-112">Это означает, что обратный вызов [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) не будет выдаваться для функции, которая является целевым объектом для вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="fae27-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="fae27-113">Значение параметра `func` недопустимо после того, как функция `FunctionTailcall2` возвращает значение, так как оно может измениться или быть уничтожено.</span><span class="sxs-lookup"><span data-stu-id="fae27-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="fae27-114">Функция `FunctionTailcall2` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="fae27-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="fae27-115">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="fae27-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="fae27-116">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="fae27-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="fae27-117">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="fae27-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="fae27-118">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="fae27-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="fae27-119">Реализация `FunctionTailcall2` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fae27-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="fae27-120">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fae27-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="fae27-121">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionTailcall2`.</span><span class="sxs-lookup"><span data-stu-id="fae27-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="fae27-122">Кроме того, функция `FunctionTailcall2` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="fae27-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fae27-123">Требования</span><span class="sxs-lookup"><span data-stu-id="fae27-123">Requirements</span></span>  
 <span data-ttu-id="fae27-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fae27-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae27-125">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="fae27-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fae27-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fae27-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fae27-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae27-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae27-128">См. также</span><span class="sxs-lookup"><span data-stu-id="fae27-128">See also</span></span>

- [<span data-ttu-id="fae27-129">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="fae27-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="fae27-130">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="fae27-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="fae27-131">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="fae27-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="fae27-132">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="fae27-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
