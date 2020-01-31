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
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866251"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="c7ac0-102">Метод ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c7ac0-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="c7ac0-103">Уведомляет профилировщик о том, что JIT-компилятор завершил компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ac0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7ac0-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ac0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7ac0-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="c7ac0-106">\[in] идентификатор скомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="c7ac0-107">\[в] значение, указывающее, успешно ли выполнена компиляция.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="c7ac0-108">\[в] значение, указывающее профилировщику на то, что блокировка повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="c7ac0-109">Значение `true`, если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="c7ac0-110">Хотя значение `true` не будет нанести вред среде выполнения, оно может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="c7ac0-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7ac0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c7ac0-111">Requirements</span></span>  
 <span data-ttu-id="c7ac0-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ac0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ac0-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7ac0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7ac0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ac0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ac0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ac0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ac0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7ac0-116">See also</span></span>

- [<span data-ttu-id="c7ac0-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c7ac0-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c7ac0-118">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c7ac0-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
