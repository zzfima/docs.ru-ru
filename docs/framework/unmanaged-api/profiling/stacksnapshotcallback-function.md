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
ms.openlocfilehash: 49e154ade91ea1a207645f924bd8aea1dbdb635c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868126"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="c02b2-102">Функция StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="c02b2-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="c02b2-103">Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c02b2-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c02b2-104">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c02b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c02b2-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="c02b2-106">окне Если это значение равно нулю, этот обратный вызов предназначен для запуска неуправляемых кадров; в противном случае это идентификатор управляемой функции, и этот обратный вызов предназначен для управляемого фрейма.</span><span class="sxs-lookup"><span data-stu-id="c02b2-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="c02b2-107">окне Значение указателя инструкций машинного кода в кадре.</span><span class="sxs-lookup"><span data-stu-id="c02b2-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="c02b2-108">окне Значение `COR_PRF_FRAME_INFO`, которое ссылается на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="c02b2-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="c02b2-109">Это значение допустимо для использования только во время этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c02b2-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c02b2-110">окне Размер структуры `CONTEXT`, на которую ссылается параметр `context`.</span><span class="sxs-lookup"><span data-stu-id="c02b2-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="c02b2-111">окне Указатель на структуру Win32 `CONTEXT`, которая представляет состояние ЦП для этого кадра.</span><span class="sxs-lookup"><span data-stu-id="c02b2-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="c02b2-112">Параметр `context` действителен, только если флаг COR_PRF_SNAPSHOT_CONTEXT был передан `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="c02b2-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="c02b2-113">окне Указатель на данные клиента, которые передаются непосредственно через `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="c02b2-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c02b2-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="c02b2-114">Remarks</span></span>  
 <span data-ttu-id="c02b2-115">Функция `StackSnapshotCallback` реализуется модулем записи профилировщика.</span><span class="sxs-lookup"><span data-stu-id="c02b2-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="c02b2-116">Необходимо ограничить сложность работы, выполненной в `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="c02b2-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="c02b2-117">Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме целевой поток может удерживать блокировки.</span><span class="sxs-lookup"><span data-stu-id="c02b2-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="c02b2-118">Если код в `StackSnapshotCallback` требует одних и тех же блокировок, может возникнуть взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="c02b2-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="c02b2-119">Метод `ICorProfilerInfo2::DoStackSnapshot` вызывает функцию `StackSnapshotCallback` один раз для каждого управляемого кадра или один раз для каждого запуска неуправляемых фреймов.</span><span class="sxs-lookup"><span data-stu-id="c02b2-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="c02b2-120">Если `StackSnapshotCallback` вызывается для запуска неуправляемых кадров, профилировщик может использовать контекст Register (на который ссылается параметр `context`) для выполнения собственного анализа неуправляемого стека.</span><span class="sxs-lookup"><span data-stu-id="c02b2-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="c02b2-121">В этом случае структура Win32 `CONTEXT` представляет состояние ЦП для последнего отправленного кадра в рамках выполнения неуправляемых кадров.</span><span class="sxs-lookup"><span data-stu-id="c02b2-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="c02b2-122">Несмотря на то, что структура Win32 `CONTEXT` включает значения для всех регистров, следует полагаться только на значения регистра указателя стека, регистра указателя кадра, регистра указателя инструкций и неизменяемых (то есть сохраненных) целочисленных регистров.</span><span class="sxs-lookup"><span data-stu-id="c02b2-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02b2-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c02b2-123">Requirements</span></span>  
 <span data-ttu-id="c02b2-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c02b2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02b2-125">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="c02b2-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c02b2-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c02b2-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c02b2-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02b2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02b2-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c02b2-128">See also</span></span>

- [<span data-ttu-id="c02b2-129">Метод DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="c02b2-129">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="c02b2-130">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="c02b2-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
