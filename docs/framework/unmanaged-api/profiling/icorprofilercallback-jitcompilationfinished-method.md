---
title: Метод ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dbf447e1325b4acaa26c9bb16d7d1a736eb20a29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453555"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="bd3db-102">Метод ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="bd3db-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="bd3db-103">Уведомляет профилировщик о завершении компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="bd3db-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd3db-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd3db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd3db-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="bd3db-106">[in] Идентификатор функции, который был скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="bd3db-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bd3db-107">[in] Значение, указывающее, была ли успешной компиляции.</span><span class="sxs-lookup"><span data-stu-id="bd3db-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="bd3db-108">[in] Значение, указывающее профилировщику ли блокировка будет влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd3db-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="bd3db-109">Значение равно `true` Если блокировок может вызвать среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="bd3db-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="bd3db-110">Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="bd3db-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd3db-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bd3db-111">Requirements</span></span>  
 <span data-ttu-id="bd3db-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd3db-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd3db-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd3db-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd3db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd3db-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd3db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bd3db-116">See Also</span></span>  
 [<span data-ttu-id="bd3db-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bd3db-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="bd3db-118">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="bd3db-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
