---
title: "Функция StackSnapshotCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackSnapshotCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: StackSnapshotCallback
helpviewer_keywords: StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32cf21fb5a76fdec4daa322d53a8eb218ae2f2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="71e3c-102">Функция StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="71e3c-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="71e3c-103">Предоставляет сведения о каждого управляемого кадра и каждом запуске неуправляемого кадра в стеке во время стека, который инициируется профилировщик [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="71e3c-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71e3c-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71e3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71e3c-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="71e3c-106">[in] Если это значение равно нулю, этот обратный вызов предназначен для управляемого кадра. в противном случае оно является идентификатором управляемой функции, и этот обратный вызов предназначен для управляемого кадра.</span><span class="sxs-lookup"><span data-stu-id="71e3c-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="71e3c-107">[in] Значение указателя инструкций машинного кода в кадре.</span><span class="sxs-lookup"><span data-stu-id="71e3c-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="71e3c-108">[in] Объект `COR_PRF_FRAME_INFO` значение, которое ссылается на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="71e3c-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="71e3c-109">Это значение является допустимым для использования только во время этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="71e3c-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="71e3c-110">[in] Размер `CONTEXT` структуры, который ссылается `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="71e3c-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="71e3c-111">[in] Указатель на объект Win32 `CONTEXT` структуры, который представляет состояние ЦП для этого кадра.</span><span class="sxs-lookup"><span data-stu-id="71e3c-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="71e3c-112">`context` Параметр допустим только в том случае, если переданный флаг COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="71e3c-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="71e3c-113">[in] Указатель на данные клиента, которые передаются непосредственно от `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="71e3c-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71e3c-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="71e3c-114">Remarks</span></span>  
 <span data-ttu-id="71e3c-115">`StackSnapshotCallback` Функция реализуется разработчиком профилировщика.</span><span class="sxs-lookup"><span data-stu-id="71e3c-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="71e3c-116">Необходимо установить ограничение сложности работы, проделанной `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="71e3c-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="71e3c-117">Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме, целевой поток может удерживать блокировки.</span><span class="sxs-lookup"><span data-stu-id="71e3c-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="71e3c-118">Если код в `StackSnapshotCallback` требуются те же блокировки, можно гарантировать взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="71e3c-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="71e3c-119">`ICorProfilerInfo2::DoStackSnapshot` Вызовы метода `StackSnapshotCallback` функцию один раз за кадр управляемого или один раз на выполнение неуправляемого кадра.</span><span class="sxs-lookup"><span data-stu-id="71e3c-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="71e3c-120">Если `StackSnapshotCallback` вызывается для запуска неуправляемых кадров, профилировщик может использовать контекст регистра (ссылается `context` параметр) для выполнения собственного неуправляемого стека.</span><span class="sxs-lookup"><span data-stu-id="71e3c-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="71e3c-121">В этом случае Win32 `CONTEXT` структура представляет состояние ЦП для наиболее недавно отправленных кадров в запуске неуправляемого кадра.</span><span class="sxs-lookup"><span data-stu-id="71e3c-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="71e3c-122">Несмотря на то что Win32 `CONTEXT` структура включает в себя значения для всех регистров, следует полагаться только на значениях регистр указателя стека, регистр указателя фрейма, регистр указателя инструкции и постоянные (хранимые) регистры целых чисел.</span><span class="sxs-lookup"><span data-stu-id="71e3c-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e3c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="71e3c-123">Requirements</span></span>  
 <span data-ttu-id="71e3c-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e3c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e3c-125">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="71e3c-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="71e3c-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71e3c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71e3c-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e3c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e3c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="71e3c-128">See Also</span></span>  
 [<span data-ttu-id="71e3c-129">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="71e3c-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="71e3c-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="71e3c-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
