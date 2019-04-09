---
title: Метод ICorProfilerCallback::ExceptionUnwindFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0451ceac3018a3bab697a8ac82f5ef84f1026c6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150791"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="ab398-102">Метод ICorProfilerCallback::ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="ab398-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="ab398-103">Уведомляет профилировщик о начале этапа очистки во время обработки исключений для раскручивания функции.</span><span class="sxs-lookup"><span data-stu-id="ab398-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab398-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab398-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab398-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab398-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ab398-106">[in] Идентификатор функции, которая развертывается.</span><span class="sxs-lookup"><span data-stu-id="ab398-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab398-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab398-107">Remarks</span></span>  
 <span data-ttu-id="ab398-108">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="ab398-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ab398-109">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ab398-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ab398-110">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ab398-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab398-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ab398-111">Requirements</span></span>  
 <span data-ttu-id="ab398-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab398-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab398-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab398-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab398-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab398-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ab398-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ab398-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab398-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ab398-116">See also</span></span>

- [<span data-ttu-id="ab398-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ab398-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ab398-118">Метод ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="ab398-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
