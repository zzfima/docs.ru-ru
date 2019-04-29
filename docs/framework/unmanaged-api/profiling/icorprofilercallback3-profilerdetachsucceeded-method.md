---
title: Метод ICorProfilerCallback3::ProfilerDetachSucceeded
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efe3070b41b1d71e0cf533a7f9f211f4c6626726
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782568"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="5e156-102">Метод ICorProfilerCallback3::ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="5e156-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="5e156-103">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="5e156-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e156-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e156-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5e156-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5e156-105">Return Value</span></span>  
 <span data-ttu-id="5e156-106">Возвращаемое значение этого обратного вызова игнорируется.</span><span class="sxs-lookup"><span data-stu-id="5e156-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e156-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e156-107">Remarks</span></span>  
 <span data-ttu-id="5e156-108">Обратный вызов `ProfilerDetachSucceeded` производится после того, как все потоки вышли из кода профилировщика.</span><span class="sxs-lookup"><span data-stu-id="5e156-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="5e156-109">Когда вызывается этот метод, профилировщик должен выполнить все завершающие задачи, которые не может выполнить его деструктор, такие как уведомление интерфейса пользователя или компонента ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="5e156-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="5e156-110">Однако профилировщик не должен вызывать функции интерфейсов, предоставляемых средой CLR во время этого обратного вызова (таких как [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) или `IMetaData*` интерфейсов).</span><span class="sxs-lookup"><span data-stu-id="5e156-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="5e156-111">Среда CLR создает запись в журнале событий приложений Windows о том, что операция отключения выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="5e156-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="5e156-112">После возврата профилировщика из этого обратного вызова среда CLR освобождает объект профилировщика и выгружает библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="5e156-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="5e156-113">Поэтому после возврата из обратного вызова профилировщик не должен выполнять никаких действий, которые вызовут выполнение кода в библиотеке DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="5e156-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="5e156-114">Например, он не должен создавать потоки или регистрировать обратные вызовы таймера.</span><span class="sxs-lookup"><span data-stu-id="5e156-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e156-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5e156-115">Requirements</span></span>  
 <span data-ttu-id="5e156-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e156-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e156-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e156-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e156-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e156-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e156-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e156-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e156-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5e156-120">See also</span></span>

- [<span data-ttu-id="5e156-121">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="5e156-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="5e156-122">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="5e156-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5e156-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5e156-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5e156-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="5e156-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
