---
title: Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: f7bc1954d11134a4515d2e29e9e0eb1626ae5d26
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863432"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="cc15a-102">Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="cc15a-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="cc15a-103">Задает реализованные профилировщиком функции, которые должны вызываться для обработчиков "Ввод", "Leave" и "таилкалл" управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="cc15a-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc15a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc15a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc15a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc15a-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="cc15a-106">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cc15a-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="cc15a-107">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave](functionleave-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cc15a-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="cc15a-108">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [функтионтаилкалл](functiontailcall-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cc15a-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc15a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="cc15a-109">Remarks</span></span>  
 <span data-ttu-id="cc15a-110">В .NET Framework версии 1,0 каждый указатель функции может иметь значение null, чтобы отключить соответствующий обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc15a-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="cc15a-111">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cc15a-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="cc15a-112">Таким образом, если профилировщик вызывает как `SetEnterLeaveFunctionHooks`, так и [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), то `SetEnterLeaveFunctionHooks2` имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="cc15a-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="cc15a-113">Метод `SetEnterLeaveFunctionHooks` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="cc15a-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc15a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cc15a-114">Requirements</span></span>  
 <span data-ttu-id="cc15a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc15a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc15a-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc15a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc15a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc15a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc15a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc15a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc15a-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc15a-119">See also</span></span>

- [<span data-ttu-id="cc15a-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cc15a-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
