---
title: Метод ICorProfilerCallback::ThreadAssignedToOSThread
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51c7235b4018fabb2ecf9c0db2800d5d9e54b327
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747143"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="fe865-102">Метод ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="fe865-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="fe865-103">Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fe865-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe865-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe865-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe865-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe865-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="fe865-106">[in] Идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="fe865-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="fe865-107">[in] Идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fe865-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe865-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe865-108">Remarks</span></span>  
 <span data-ttu-id="fe865-109">`ThreadAssignedToOSThread` Обратный вызов существует таким образом, профилировщик может обеспечить точное сопоставление волокна потоков операционной системы в управляемые потоки.</span><span class="sxs-lookup"><span data-stu-id="fe865-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe865-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fe865-110">Requirements</span></span>  
 <span data-ttu-id="fe865-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe865-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe865-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe865-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fe865-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe865-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe865-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe865-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe865-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fe865-115">See also</span></span>

- [<span data-ttu-id="fe865-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fe865-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
