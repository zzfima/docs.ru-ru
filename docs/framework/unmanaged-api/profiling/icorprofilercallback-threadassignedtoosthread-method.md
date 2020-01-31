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
ms.openlocfilehash: 0e8c91f65d4ebec07689a42d4517fc100fce136d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865848"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="e220e-102">Метод ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="e220e-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="e220e-103">Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e220e-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e220e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e220e-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e220e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e220e-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="e220e-106">окне Идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="e220e-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="e220e-107">окне Идентификатор потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e220e-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e220e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e220e-108">Remarks</span></span>  
 <span data-ttu-id="e220e-109">Функция обратного вызова `ThreadAssignedToOSThread` существует, чтобы профилировщик мог поддерживать точное сопоставление по волокнам потоков операционной системы с управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="e220e-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e220e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e220e-110">Requirements</span></span>  
 <span data-ttu-id="e220e-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e220e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e220e-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e220e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e220e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e220e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e220e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e220e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e220e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e220e-115">See also</span></span>

- [<span data-ttu-id="e220e-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e220e-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
