---
title: Метод ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91bc626e2c75cd7eb2eafad0fc26d343e5b278e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530736"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="55139-102">Метод ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="55139-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="55139-103">Уведомляет профилировщик, функция, которая была just-in-time (JIT)-компиляции был удален из памяти.</span><span class="sxs-lookup"><span data-stu-id="55139-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55139-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55139-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55139-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55139-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="55139-106">[in] Идентификатор функции, который был удален.</span><span class="sxs-lookup"><span data-stu-id="55139-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55139-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="55139-107">Remarks</span></span>  
 <span data-ttu-id="55139-108">При вызове удаленной функции, профилировщик получит новые события JIT-компиляции при ее повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="55139-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="55139-109">В настоящее время компилятор JIT среды CLR не удаляет функции из памяти, поэтому этот обратный вызов в настоящее время не используется и не будут приниматься профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="55139-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="55139-110">Значение `functionId` недопустима до ее повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="55139-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="55139-111">Если функция перекомпилируется, же `functionId` значение будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="55139-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55139-112">Требования</span><span class="sxs-lookup"><span data-stu-id="55139-112">Requirements</span></span>  
 <span data-ttu-id="55139-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55139-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55139-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55139-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55139-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55139-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55139-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55139-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55139-117">См. также</span><span class="sxs-lookup"><span data-stu-id="55139-117">See also</span></span>
- [<span data-ttu-id="55139-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="55139-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
