---
title: Метод ICLRTask::YieldTask
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
ms.openlocfilehash: 43f2048c8ab85fa7e94f73aad430400ad4c8352f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124583"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="85415-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="85415-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="85415-103">Запрашивает, что среда CLR должна отложить задачу, представляемую текущим экземпляром [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) , и сделать процессор доступным для других задач.</span><span class="sxs-lookup"><span data-stu-id="85415-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85415-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85415-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="85415-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85415-105">Return Value</span></span>  
  
|<span data-ttu-id="85415-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85415-106">HRESULT</span></span>|<span data-ttu-id="85415-107">Описание</span><span class="sxs-lookup"><span data-stu-id="85415-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85415-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="85415-108">S_OK</span></span>|<span data-ttu-id="85415-109">`YieldTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="85415-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="85415-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85415-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85415-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="85415-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85415-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85415-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85415-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="85415-113">The call timed out.</span></span>|  
|<span data-ttu-id="85415-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85415-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85415-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="85415-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85415-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85415-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85415-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="85415-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85415-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85415-118">E_FAIL</span></span>|<span data-ttu-id="85415-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="85415-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85415-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="85415-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85415-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85415-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85415-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="85415-122">Remarks</span></span>  
 <span data-ttu-id="85415-123">Узел вызывает `YieldTask`, чтобы запросить ресурсы процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="85415-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="85415-124">Этот метод в основном предназначен для того, чтобы долго выполняемый код выдать время ЦП.</span><span class="sxs-lookup"><span data-stu-id="85415-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="85415-125">Среда выполнения пытается разместить задачу, которая представляет текущий экземпляр `ICLRTask`, в состоянии, где оно может подавать время обработки, но не гарантирует успеха.</span><span class="sxs-lookup"><span data-stu-id="85415-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85415-126">Требования</span><span class="sxs-lookup"><span data-stu-id="85415-126">Requirements</span></span>  
 <span data-ttu-id="85415-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85415-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85415-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85415-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85415-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="85415-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85415-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85415-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85415-131">См. также</span><span class="sxs-lookup"><span data-stu-id="85415-131">See also</span></span>

- [<span data-ttu-id="85415-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="85415-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="85415-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="85415-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="85415-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="85415-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="85415-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="85415-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
