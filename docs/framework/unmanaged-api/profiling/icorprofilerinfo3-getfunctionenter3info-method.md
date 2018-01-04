---
title: "Метод ICorProfilerInfo3::GetFunctionEnter3Info"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b7053f526d415dbaef872e37d139d25ae5ac462
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="4bec3-102">Метод ICorProfilerInfo3::GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="4bec3-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="4bec3-103">Предоставляет кадр и сведения стека функции, которая сообщается профилировщику [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4bec3-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="4bec3-104">Этот метод может быть вызван только во время обратного вызова `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="4bec3-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bec3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bec3-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bec3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bec3-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4bec3-107">[in] `FunctionID` функции, которая вводится.</span><span class="sxs-lookup"><span data-stu-id="4bec3-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="4bec3-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="4bec3-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="4bec3-109">Профилировщик должен предоставлять тот же `eltInfo` , указанный по [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4bec3-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="4bec3-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="4bec3-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="4bec3-111">Этот дескриптор допустим только во время обратного вызова `FunctionEnter3WithInfo`, в котором профилировщик вызывал метод `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="4bec3-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="4bec3-112">[in, out] Указатель на общий размер в байтах для [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) структуры (и для всех дополнительных [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структур для диапазона аргументов, на который указывает `pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="4bec3-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="4bec3-113">Если указанный размер недостаточен, то возвращается значение ERROR_INSUFFICIENT_BUFFER, и ожидаемый размер сохраняется в `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="4bec3-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="4bec3-114">Чтобы вызвать `GetFunctionEnter3Info` только для получения ожидаемого значения для `*pcbArgumentInfo`, установите `*pcbArgumentInfo`= 0 и `pArgumentInfo`= NULL.</span><span class="sxs-lookup"><span data-stu-id="4bec3-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="4bec3-115">[out] Указатель на [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) структуру, которая описывает расположения аргументов функции в памяти, в порядке слева направо.</span><span class="sxs-lookup"><span data-stu-id="4bec3-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bec3-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bec3-116">Remarks</span></span>  
 <span data-ttu-id="4bec3-117">Профилировщик должен выделить достаточно места для структуры `COR_PRF_FUNCTION_ARGUMENT_INFO` проверяемой функции, и должен указать размер в параметре `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="4bec3-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bec3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4bec3-118">Requirements</span></span>  
 <span data-ttu-id="4bec3-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bec3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bec3-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bec3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bec3-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bec3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bec3-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bec3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bec3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4bec3-123">See Also</span></span>  
 [<span data-ttu-id="4bec3-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4bec3-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="4bec3-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4bec3-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="4bec3-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4bec3-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="4bec3-127">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="4bec3-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="4bec3-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="4bec3-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="4bec3-129">Профилирование</span><span class="sxs-lookup"><span data-stu-id="4bec3-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
