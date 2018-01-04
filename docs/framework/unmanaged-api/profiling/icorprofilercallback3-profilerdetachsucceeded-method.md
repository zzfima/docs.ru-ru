---
title: "Метод ICorProfilerCallback3::ProfilerDetachSucceeded"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d06671917094752287836800ebc492d5f0a5b595
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="8d3e5-102">Метод ICorProfilerCallback3::ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="8d3e5-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="8d3e5-103">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d3e5-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d3e5-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8d3e5-105">Return Value</span></span>  
 <span data-ttu-id="8d3e5-106">Возвращаемое значение этого обратного вызова игнорируется.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d3e5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d3e5-107">Remarks</span></span>  
 <span data-ttu-id="8d3e5-108">Обратный вызов `ProfilerDetachSucceeded` производится после того, как все потоки вышли из кода профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="8d3e5-109">Когда вызывается этот метод, профилировщик должен выполнить все завершающие задачи, которые не может выполнить его деструктор, такие как уведомление интерфейса пользователя или компонента ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="8d3e5-110">Однако профилировщик не должен вызывать функции интерфейсов, предоставляемых средой CLR во время этого обратного вызова (таких как [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) или `IMetaData*` интерфейсов).</span><span class="sxs-lookup"><span data-stu-id="8d3e5-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="8d3e5-111">Среда CLR создает запись в журнале событий приложений Windows о том, что операция отключения выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="8d3e5-112">После возврата профилировщика из этого обратного вызова среда CLR освобождает объект профилировщика и выгружает библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="8d3e5-113">Поэтому после возврата из обратного вызова профилировщик не должен выполнять никаких действий, которые вызовут выполнение кода в библиотеке DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="8d3e5-114">Например, он не должен создавать потоки или регистрировать обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="8d3e5-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3e5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8d3e5-115">Requirements</span></span>  
 <span data-ttu-id="8d3e5-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d3e5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d3e5-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d3e5-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d3e5-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d3e5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d3e5-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d3e5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3e5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8d3e5-120">See Also</span></span>  
 [<span data-ttu-id="8d3e5-121">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="8d3e5-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="8d3e5-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="8d3e5-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="8d3e5-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="8d3e5-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8d3e5-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="8d3e5-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
