---
title: Метод ICLRTask::Abort
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124919"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="14f3f-102">Метод ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="14f3f-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="14f3f-103">Запрашивает прекращение средой CLR задачи, которую представляет текущий экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="14f3f-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14f3f-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="14f3f-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14f3f-105">Return Value</span></span>  
  
|<span data-ttu-id="14f3f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14f3f-106">HRESULT</span></span>|<span data-ttu-id="14f3f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="14f3f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14f3f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="14f3f-108">S_OK</span></span>|<span data-ttu-id="14f3f-109">`Abort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="14f3f-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="14f3f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14f3f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14f3f-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="14f3f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14f3f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14f3f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14f3f-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="14f3f-113">The call timed out.</span></span>|  
|<span data-ttu-id="14f3f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14f3f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14f3f-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="14f3f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14f3f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14f3f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14f3f-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="14f3f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14f3f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14f3f-118">E_FAIL</span></span>|<span data-ttu-id="14f3f-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="14f3f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14f3f-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="14f3f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14f3f-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14f3f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14f3f-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="14f3f-122">Remarks</span></span>  
 <span data-ttu-id="14f3f-123">Среда CLR вызывает <xref:System.Threading.ThreadAbortException>, когда узел вызывает `Abort`.</span><span class="sxs-lookup"><span data-stu-id="14f3f-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="14f3f-124">Он возвращает сразу после инициализации сведений об исключении, не дожидаясь выполнения пользовательского кода, например методов завершения или механизмов обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="14f3f-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="14f3f-125">Вызовы к `Abort`, таким же, быстро возвращают.</span><span class="sxs-lookup"><span data-stu-id="14f3f-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f3f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="14f3f-126">Requirements</span></span>  
 <span data-ttu-id="14f3f-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14f3f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14f3f-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="14f3f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14f3f-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="14f3f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14f3f-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f3f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f3f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="14f3f-131">See also</span></span>

- [<span data-ttu-id="14f3f-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="14f3f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="14f3f-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="14f3f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="14f3f-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="14f3f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="14f3f-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="14f3f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
