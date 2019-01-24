---
title: Функция FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71bde7534e391872fe85c2a22142cbc3dc2725e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680953"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="d5430-102">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d5430-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="d5430-103">Уведомляет профилировщик о заданному идентификатору функции может быть альтернативный идентификатор для использования в [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), и [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), или[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d5430-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), or[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="d5430-104">`FunctionIDMapper2` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d5430-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5430-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5430-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5430-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5430-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="d5430-107">[in] Идентификатор функции для повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="d5430-107">[in] The function identifier to be remapped.</span></span>  
  
 `clientData`  
 <span data-ttu-id="d5430-108">[in] Указатель на данные, используемые для однозначного определения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5430-108">[in] A pointer to data that is used to disambiguate among runtimes.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="d5430-109">[out] Указатель на значение, заданное профилировщиком: `true`, если профилировщик хочет получать обратные вызовы `FunctionEnter3`, `FunctionLeave3` и `FunctionTailcall3` или `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo` и `FunctionTailcall3WithInfo`;  `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="d5430-109">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5430-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5430-110">Return Value</span></span>  
 <span data-ttu-id="d5430-111">Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции.</span><span class="sxs-lookup"><span data-stu-id="d5430-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="d5430-112">Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d5430-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="d5430-113">В противном случае возвращаемое значение null приводит к непредсказуемым результатам, включая возможное прерывание процесса.</span><span class="sxs-lookup"><span data-stu-id="d5430-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5430-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5430-114">Remarks</span></span>  
 <span data-ttu-id="d5430-115">Этот метод расширяет [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) функция содержит дополнительный параметр, который используется для передачи данных клиента.</span><span class="sxs-lookup"><span data-stu-id="d5430-115">This method extends the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="d5430-116">Эти данные клиента служат для однозначного определения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5430-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5430-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d5430-117">Requirements</span></span>  
 <span data-ttu-id="d5430-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5430-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5430-119">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d5430-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d5430-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5430-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5430-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5430-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5430-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d5430-122">See also</span></span>
- [<span data-ttu-id="d5430-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d5430-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d5430-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d5430-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="d5430-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="d5430-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="d5430-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="d5430-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="d5430-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="d5430-127">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d5430-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5430-128">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="d5430-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5430-129">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d5430-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d5430-130">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d5430-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="d5430-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
