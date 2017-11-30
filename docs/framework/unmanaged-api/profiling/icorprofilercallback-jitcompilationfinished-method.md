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
ms.openlocfilehash: 9719ce1474c2111692c6176655b75bd2d7edf923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="4a813-102">Метод ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="4a813-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="4a813-103">Уведомляет профилировщик о завершении компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="4a813-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a813-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a813-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a813-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a813-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4a813-106">[in] Идентификатор функции, который был скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="4a813-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4a813-107">[in] Значение, указывающее, была ли успешной компиляции.</span><span class="sxs-lookup"><span data-stu-id="4a813-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4a813-108">[in] Значение, указывающее профилировщику ли блокировка будет влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a813-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="4a813-109">Значение равно `true` Если блокировок может вызвать среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="4a813-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="4a813-110">Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="4a813-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a813-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4a813-111">Requirements</span></span>  
 <span data-ttu-id="4a813-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a813-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a813-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a813-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a813-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a813-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a813-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a813-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a813-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4a813-116">See Also</span></span>  
 [<span data-ttu-id="4a813-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4a813-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4a813-118">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="4a813-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
