---
title: "Метод ICorProfilerCallback::JITCompilationFinished"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9bd1a163fa5e941c68c5dd8d7d3221e8a5aa3df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="a3ea8-102">Метод ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="a3ea8-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="a3ea8-103">Уведомляет профилировщик о завершении компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a3ea8-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ea8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3ea8-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3ea8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3ea8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a3ea8-106">[in] Идентификатор функции, который был скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="a3ea8-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a3ea8-107">[in] Значение, указывающее, была ли успешной компиляции.</span><span class="sxs-lookup"><span data-stu-id="a3ea8-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a3ea8-108">[in] Значение, указывающее профилировщику ли блокировка будет влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3ea8-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="a3ea8-109">Значение равно `true` Если блокировок может вызвать среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="a3ea8-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a3ea8-110">Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="a3ea8-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ea8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a3ea8-111">Requirements</span></span>  
 <span data-ttu-id="a3ea8-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3ea8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ea8-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3ea8-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3ea8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ea8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ea8-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ea8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ea8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a3ea8-116">See Also</span></span>  
 [<span data-ttu-id="a3ea8-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a3ea8-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a3ea8-118">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="a3ea8-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
