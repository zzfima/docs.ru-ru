---
title: "Метод ICorProfilerCallback::Shutdown"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="f2a1c-102">Метод ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="f2a1c-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="f2a1c-103">Уведомляет профилировщик о том, что приложение завершает работу.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2a1c-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f2a1c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2a1c-105">Remarks</span></span>  
 <span data-ttu-id="f2a1c-106">Профилировщик кода не может безопасно вызывать методы [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейса после `Shutdown` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="f2a1c-107">Все вызовы `ICorProfilerInfo` метода приводят к неопределенному поведению после `Shutdown` возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="f2a1c-108">Некоторые неизменяемые события могут происходить после завершения работы; Профилировщик следует позаботиться о возвращают немедленно в том случае, когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="f2a1c-109">`Shutdown` Метод будет вызываться только в том случае, если управляемого приложения, для которой производится профилирование запущен как управляемый код (то есть управляется начальный кадр в стеке процесса).</span><span class="sxs-lookup"><span data-stu-id="f2a1c-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="f2a1c-110">Если приложение запущен как неуправляемый код, но позже осуществлен переход в управляемом коде, создавая экземпляр среды common language runtime (CLR), затем `Shutdown` не будет вызван.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="f2a1c-111">В этих случаях профилировщик должен включить в собственной библиотеке `DllMain` подпрограмму, которая использует DLL_PROCESS_DETACH значение освободить все ресурсы и выполнить процесса очистки данных, например очистки трассировок на диске и т. д.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="f2a1c-112">Как правило профилировщик должен быть рассчитан неожиданных выключений.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="f2a1c-113">Например, процесс может быть прервана Win32 `TerminateProcess` метод (объявлено в Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="f2a1c-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="f2a1c-114">В других случаях CLR будет прерывать определенные управляемые потоки (фоновые потоки) без предоставления надлежащих сообщений об удалении для них.</span><span class="sxs-lookup"><span data-stu-id="f2a1c-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2a1c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f2a1c-115">Requirements</span></span>  
 <span data-ttu-id="f2a1c-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2a1c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a1c-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2a1c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2a1c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2a1c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2a1c-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a1c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a1c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f2a1c-120">See Also</span></span>  
 [<span data-ttu-id="f2a1c-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f2a1c-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f2a1c-122">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="f2a1c-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
