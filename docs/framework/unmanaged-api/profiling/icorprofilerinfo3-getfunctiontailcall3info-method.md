---
title: Метод ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: e7a25fce945504cff0d07f499ae4bb79378e9f3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449702"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="93867-102">Метод ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="93867-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="93867-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span><span class="sxs-lookup"><span data-stu-id="93867-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="93867-104">Этот метод может быть вызван только во время обратного вызова `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="93867-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93867-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93867-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93867-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="93867-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="93867-107">[in] The `FunctionID` of the function that is returning.</span><span class="sxs-lookup"><span data-stu-id="93867-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="93867-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="93867-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="93867-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span><span class="sxs-lookup"><span data-stu-id="93867-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="93867-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="93867-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="93867-111">Этот дескриптор допустим только во время обратного вызова `FunctionTailcall3WithInfo`, в котором профилировщик вызывал метод `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="93867-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93867-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="93867-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93867-113">Требования</span><span class="sxs-lookup"><span data-stu-id="93867-113">Requirements</span></span>  
 <span data-ttu-id="93867-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93867-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93867-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="93867-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="93867-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93867-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93867-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93867-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93867-118">См. также</span><span class="sxs-lookup"><span data-stu-id="93867-118">See also</span></span>

- [<span data-ttu-id="93867-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="93867-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="93867-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="93867-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="93867-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="93867-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="93867-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="93867-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="93867-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="93867-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="93867-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="93867-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
