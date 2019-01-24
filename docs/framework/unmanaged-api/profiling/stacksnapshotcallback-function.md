---
title: Функция StackSnapshotCallback
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e73afa7ef33e12d6bc658c944c79ce1bc4f94f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572431"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="63135-102">Функция StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="63135-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="63135-103">Предоставляет сведения о каждого управляемого кадра и каждом запуске неуправляемых фреймов в стеке во время стека, который инициируется профилировщик [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="63135-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63135-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63135-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="63135-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63135-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="63135-106">[in] Если это значение равно нулю, этот обратный вызов предназначен для неуправляемых фреймов; в противном случае он представляет собой идентификатор управляемой функции, и этот обратный вызов является для управляемого фрейма.</span><span class="sxs-lookup"><span data-stu-id="63135-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="63135-107">[in] Значение указателя инструкции машинного кода в фрейме.</span><span class="sxs-lookup"><span data-stu-id="63135-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="63135-108">[in] Объект `COR_PRF_FRAME_INFO` значение, которое ссылается на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="63135-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="63135-109">Это значение является допустимым для использования только во время этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="63135-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="63135-110">[in] Размер `CONTEXT` структуру, которая ссылается `context` параметра.</span><span class="sxs-lookup"><span data-stu-id="63135-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="63135-111">[in] Указатель на Win32 `CONTEXT` структура, представляющая состояние ЦП для данного кадра.</span><span class="sxs-lookup"><span data-stu-id="63135-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="63135-112">`context` Параметр допустим только в том случае, если был передан флаг COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="63135-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="63135-113">[in] Указатель на данные клиента, который передается напрямую через из `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="63135-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63135-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="63135-114">Remarks</span></span>  
 <span data-ttu-id="63135-115">`StackSnapshotCallback` Функция реализуется разработчиком профилировщика.</span><span class="sxs-lookup"><span data-stu-id="63135-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="63135-116">Необходимо ограничить сложность работы, проделанной `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="63135-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="63135-117">Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме, целевой поток может блокироваться.</span><span class="sxs-lookup"><span data-stu-id="63135-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="63135-118">Если код в `StackSnapshotCallback` требуются те же блокировки, взаимоблокировки неприятности.</span><span class="sxs-lookup"><span data-stu-id="63135-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="63135-119">`ICorProfilerInfo2::DoStackSnapshot` Вызовы методов `StackSnapshotCallback` функцию один раз в управляемый блок кода, или один раз на серию неуправляемых фреймов.</span><span class="sxs-lookup"><span data-stu-id="63135-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="63135-120">Если `StackSnapshotCallback` вызывается для запуска неуправляемых фреймов, профилировщик может использовать регистров (ссылается `context` параметр) для выполнения свой собственный неуправляемый разбор стека.</span><span class="sxs-lookup"><span data-stu-id="63135-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="63135-121">В данном случае Win32 `CONTEXT` структура представляет состояние ЦП для наиболее недавно отправленных кадра в серию неуправляемых фреймов.</span><span class="sxs-lookup"><span data-stu-id="63135-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="63135-122">Несмотря на то что Win32 `CONTEXT` структура включает значения для всех регистров, следует полагаться только на значениях регистр указателя стека, регистр указателя кадра, регистр указателя инструкции и постоянные (хранимые) целочисленных регистров.</span><span class="sxs-lookup"><span data-stu-id="63135-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63135-123">Требования</span><span class="sxs-lookup"><span data-stu-id="63135-123">Requirements</span></span>  
 <span data-ttu-id="63135-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63135-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63135-125">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="63135-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="63135-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63135-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63135-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63135-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63135-128">См. также</span><span class="sxs-lookup"><span data-stu-id="63135-128">See also</span></span>
- [<span data-ttu-id="63135-129">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="63135-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="63135-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="63135-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
