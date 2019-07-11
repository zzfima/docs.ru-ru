---
title: Метод ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d63dd911a5f674a3ce0b02ec78de443c7aebf84
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747170"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="d43b4-102">Метод ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="d43b4-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="d43b4-103">Уведомляет профилировщик, что приложение завершает работу.</span><span class="sxs-lookup"><span data-stu-id="d43b4-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d43b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d43b4-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d43b4-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d43b4-105">Remarks</span></span>  
 <span data-ttu-id="d43b4-106">Профилировщик кода не может безопасно вызывать методы из [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейс после `Shutdown` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="d43b4-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="d43b4-107">Все вызовы `ICorProfilerInfo` метода приводят к неопределенному поведению после `Shutdown` возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="d43b4-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="d43b4-108">Некоторые неизменяемые события по-прежнему возникает после завершения работы; Профилировщик должен позаботиться о возвращать немедленно в том случае, когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="d43b4-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="d43b4-109">`Shutdown` Метод будет вызываться только в том случае, если управляемое приложение, в которой производится профилирование запущен как управляемый код (то есть управляется начальный кадр в стеке процесса).</span><span class="sxs-lookup"><span data-stu-id="d43b4-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="d43b4-110">Если приложение запущен как неуправляемый код, но позже осуществлен переход в управляемом коде, тем самым создавая экземпляра общеязыковой среды выполнения (CLR), затем `Shutdown` не будет вызван.</span><span class="sxs-lookup"><span data-stu-id="d43b4-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="d43b4-111">В этих случаях профилировщик должен включать в собственной библиотеке `DllMain` подпрограмму, которая использует DLL_PROCESS_DETACH значение освободить все ресурсы и выполнить процесса очистки данных, например очистки трассировок на диске и т. д.</span><span class="sxs-lookup"><span data-stu-id="d43b4-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="d43b4-112">Как правило профилировщик должен быть рассчитан неожиданных выключений.</span><span class="sxs-lookup"><span data-stu-id="d43b4-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="d43b4-113">Например, процесс может быть приостановлена из-за Win32 `TerminateProcess` метод (объявлен в Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="d43b4-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="d43b4-114">В других случаях CLR будет прерывать определенные управляемые потоки (фоновые потоки) без обеспечения надлежащих сообщений об удалении для них.</span><span class="sxs-lookup"><span data-stu-id="d43b4-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d43b4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d43b4-115">Requirements</span></span>  
 <span data-ttu-id="d43b4-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d43b4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d43b4-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d43b4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d43b4-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d43b4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d43b4-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d43b4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43b4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d43b4-120">See also</span></span>

- [<span data-ttu-id="d43b4-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d43b4-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d43b4-122">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="d43b4-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
