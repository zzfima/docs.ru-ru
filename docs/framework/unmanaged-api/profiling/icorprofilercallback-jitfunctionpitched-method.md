---
title: "Метод ICorProfilerCallback::JITFunctionPitched"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48432911d7844e6519689961c985da37219179a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="7fb25-102">Метод ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="7fb25-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="7fb25-103">Уведомляет профилировщик, функция, которая была время JIT-компиляции был удален из памяти.</span><span class="sxs-lookup"><span data-stu-id="7fb25-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fb25-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fb25-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fb25-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7fb25-106">[in] Идентификатор функции, которая была удалена.</span><span class="sxs-lookup"><span data-stu-id="7fb25-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fb25-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7fb25-107">Remarks</span></span>  
 <span data-ttu-id="7fb25-108">При вызове удаленной функции профилировщик получит новые события JIT-компиляции, при ее повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="7fb25-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="7fb25-109">В настоящее время компилятор JIT среды CLR не удаляет функции из памяти, поэтому этот обратный вызов в настоящее время не используется и не получит профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="7fb25-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="7fb25-110">Значение `functionId` недопустима до ее повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="7fb25-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="7fb25-111">Если функция перекомпилируется, же `functionId` будет использовано значение.</span><span class="sxs-lookup"><span data-stu-id="7fb25-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fb25-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7fb25-112">Requirements</span></span>  
 <span data-ttu-id="7fb25-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fb25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb25-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fb25-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fb25-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fb25-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fb25-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb25-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7fb25-117">See Also</span></span>  
 [<span data-ttu-id="7fb25-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7fb25-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
