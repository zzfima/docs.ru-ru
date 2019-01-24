---
title: Метод ICorProfilerInfo4::GetFunctionFromIP2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bded97c23013e60bf2d3c32c4eb25285870977e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554196"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="67938-102">Метод ICorProfilerInfo4::GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="67938-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="67938-103">Сопоставляет указатель инструкции управляемого кода для перекомпиляции JIT версию функции.</span><span class="sxs-lookup"><span data-stu-id="67938-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67938-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67938-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67938-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67938-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="67938-106">[in] Указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="67938-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="67938-107">[out] Идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="67938-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="67938-108">[out] Идентификация версию функции перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="67938-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67938-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="67938-109">Remarks</span></span>  
 <span data-ttu-id="67938-110">`GetFunctionFromIP2` аналогичен `GetFunctionFromIP`, за исключением того, что он получает идентификатор перекомпиляции JIT, а не идентификатор функции, функции, которая содержит указанный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="67938-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67938-111">`GetFunctionFromIP2` можно запустить сбор мусора, тогда как `GetFunctionFromIP` не будет.</span><span class="sxs-lookup"><span data-stu-id="67938-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="67938-112">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="67938-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67938-113">Требования</span><span class="sxs-lookup"><span data-stu-id="67938-113">Requirements</span></span>  
 <span data-ttu-id="67938-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67938-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67938-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67938-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67938-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67938-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67938-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67938-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67938-118">См. также</span><span class="sxs-lookup"><span data-stu-id="67938-118">See also</span></span>
- [<span data-ttu-id="67938-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="67938-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
