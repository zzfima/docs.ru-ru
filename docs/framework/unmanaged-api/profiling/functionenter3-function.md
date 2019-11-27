---
title: Функция FunctionEnter3
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: fd224279b3df6c9e8e55cd81ebfbf2e5ea2428d5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440777"
---
# <a name="functionenter3-function"></a><span data-ttu-id="9f9fe-102">Функция FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9f9fe-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="9f9fe-103">Уведомляет профилировщик о передаче управления в функцию.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f9fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f9fe-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f9fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f9fe-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="9f9fe-106">окне Идентификатор функции, которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f9fe-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9f9fe-107">Remarks</span></span>  
 <span data-ttu-id="9f9fe-108">Функция обратного вызова `FunctionEnter3` уведомляет профилировщик о вызове функций, но не поддерживает проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="9f9fe-109">Чтобы зарегистрировать реализацию этой функции, используйте [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9f9fe-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="9f9fe-110">Функция `FunctionEnter3` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="9f9fe-111">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="9f9fe-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="9f9fe-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="9f9fe-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="9f9fe-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="9f9fe-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f9fe-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9f9fe-115">Requirements</span></span>  
 <span data-ttu-id="9f9fe-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f9fe-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f9fe-117">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="9f9fe-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9f9fe-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f9fe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f9fe-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f9fe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9fe-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9f9fe-120">See also</span></span>

- [<span data-ttu-id="9f9fe-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9f9fe-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="9f9fe-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="9f9fe-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="9f9fe-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9f9fe-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="9f9fe-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9f9fe-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="9f9fe-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9f9fe-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="9f9fe-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="9f9fe-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="9f9fe-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9f9fe-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="9f9fe-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="9f9fe-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="9f9fe-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="9f9fe-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="9f9fe-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="9f9fe-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
