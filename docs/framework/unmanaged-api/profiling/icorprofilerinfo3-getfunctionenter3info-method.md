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
ms.openlocfilehash: a75f76af924c3e75d280c36fb5f436498dc6c862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="009d8-102">Метод ICorProfilerInfo3::GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="009d8-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="009d8-103">Предоставляет кадр и сведения стека функции, которая сообщается профилировщику [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="009d8-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="009d8-104">Этот метод может быть вызван только во время обратного вызова `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="009d8-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="009d8-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="009d8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="009d8-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="009d8-107">[in] `FunctionID` функции, которая вводится.</span><span class="sxs-lookup"><span data-stu-id="009d8-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="009d8-108">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="009d8-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="009d8-109">Профилировщик должен предоставлять тот же `eltInfo` , указанный по [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="009d8-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="009d8-110">[out] Непрозрачный дескриптор, представляющий универсальные сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="009d8-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="009d8-111">Этот дескриптор допустим только во время обратного вызова `FunctionEnter3WithInfo`, в котором профилировщик вызывал метод `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="009d8-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="009d8-112">[in, out] Указатель на общий размер в байтах для [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) структуры (и для всех дополнительных [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структур для диапазона аргументов, на который указывает `pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="009d8-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="009d8-113">Если указанный размер недостаточен, то возвращается значение ERROR_INSUFFICIENT_BUFFER, и ожидаемый размер сохраняется в `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="009d8-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="009d8-114">Чтобы вызвать `GetFunctionEnter3Info` только для получения ожидаемого значения для `*pcbArgumentInfo`, установите `*pcbArgumentInfo`= 0 и `pArgumentInfo`= NULL.</span><span class="sxs-lookup"><span data-stu-id="009d8-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="009d8-115">[out] Указатель на [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) структуру, которая описывает расположения аргументов функции в памяти, в порядке слева направо.</span><span class="sxs-lookup"><span data-stu-id="009d8-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="009d8-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="009d8-116">Remarks</span></span>  
 <span data-ttu-id="009d8-117">Профилировщик должен выделить достаточно места для структуры `COR_PRF_FUNCTION_ARGUMENT_INFO` проверяемой функции, и должен указать размер в параметре `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="009d8-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009d8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="009d8-118">Requirements</span></span>  
 <span data-ttu-id="009d8-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009d8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009d8-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="009d8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="009d8-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="009d8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="009d8-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009d8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009d8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="009d8-123">See Also</span></span>  
 [<span data-ttu-id="009d8-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="009d8-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="009d8-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="009d8-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="009d8-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="009d8-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="009d8-127">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="009d8-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="009d8-128">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="009d8-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="009d8-129">Профилирование</span><span class="sxs-lookup"><span data-stu-id="009d8-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
