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
ms.openlocfilehash: 51f8768fc3cd73f0fd5bdb84842af03b900fafdf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495355"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="27220-102">Метод ICorProfilerInfo4::GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="27220-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="27220-103">Сопоставляет указатель инструкции управляемого кода для перекомпиляции JIT версию функции.</span><span class="sxs-lookup"><span data-stu-id="27220-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27220-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27220-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27220-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27220-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="27220-106">[in] Указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="27220-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="27220-107">[out] Идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="27220-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="27220-108">[out] Идентификация версию функции перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="27220-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27220-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="27220-109">Remarks</span></span>  
 <span data-ttu-id="27220-110">`GetFunctionFromIP2` аналогичен `GetFunctionFromIP`, за исключением того, что он получает идентификатор перекомпиляции JIT, а не идентификатор функции, функции, которая содержит указанный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="27220-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27220-111">`GetFunctionFromIP2` можно запустить сбор мусора, тогда как `GetFunctionFromIP` не будет.</span><span class="sxs-lookup"><span data-stu-id="27220-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="27220-112">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="27220-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27220-113">Требования</span><span class="sxs-lookup"><span data-stu-id="27220-113">Requirements</span></span>  
 <span data-ttu-id="27220-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27220-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27220-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27220-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27220-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27220-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27220-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27220-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27220-118">См. также</span><span class="sxs-lookup"><span data-stu-id="27220-118">See also</span></span>
- [<span data-ttu-id="27220-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="27220-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
