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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74f0e6e39f99c9e6981066e6a3171bb9508cf1a5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782137"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="43c5d-102">Метод ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="43c5d-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="43c5d-103">Предоставляет кадр стека функции, которая сообщается профилировщику [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="43c5d-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="43c5d-104">Этот метод может быть вызван только во время обратного вызова `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="43c5d-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c5d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43c5d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c5d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="43c5d-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="43c5d-107">[in] `FunctionID` Функции, которая возвращает.</span><span class="sxs-lookup"><span data-stu-id="43c5d-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="43c5d-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="43c5d-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="43c5d-109">Профилировщик должен предоставлять тот же `eltInfo` , которому был назначен профилировщику `FunctionTailcall3WithInfo` функции.</span><span class="sxs-lookup"><span data-stu-id="43c5d-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="43c5d-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="43c5d-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="43c5d-111">Этот дескриптор допустим только во время обратного вызова `FunctionTailcall3WithInfo`, в котором профилировщик вызывал метод `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="43c5d-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c5d-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="43c5d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c5d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="43c5d-113">Requirements</span></span>  
 <span data-ttu-id="43c5d-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c5d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c5d-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43c5d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43c5d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c5d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c5d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c5d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c5d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="43c5d-118">See also</span></span>

- [<span data-ttu-id="43c5d-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="43c5d-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="43c5d-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="43c5d-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="43c5d-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="43c5d-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="43c5d-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="43c5d-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="43c5d-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="43c5d-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="43c5d-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="43c5d-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
