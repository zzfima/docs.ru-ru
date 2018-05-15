---
title: Метод IHostIoCompletionManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a810f3a25dc90ddb234c70ca3fa5130039350136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="b28ed-102">Метод IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b28ed-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="b28ed-103">Задает максимальное число потоков, выделяемых основным приложением для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b28ed-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b28ed-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b28ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b28ed-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="b28ed-106">[in] Максимальное количество потоков для выделения запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b28ed-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28ed-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b28ed-107">Return Value</span></span>  
  
|<span data-ttu-id="b28ed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b28ed-108">HRESULT</span></span>|<span data-ttu-id="b28ed-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b28ed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b28ed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b28ed-110">S_OK</span></span>|<span data-ttu-id="b28ed-111">`SetMaxThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b28ed-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b28ed-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b28ed-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b28ed-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b28ed-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b28ed-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b28ed-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b28ed-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b28ed-115">The call timed out.</span></span>|  
|<span data-ttu-id="b28ed-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b28ed-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b28ed-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b28ed-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b28ed-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b28ed-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b28ed-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b28ed-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b28ed-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b28ed-120">E_FAIL</span></span>|<span data-ttu-id="b28ed-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b28ed-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b28ed-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b28ed-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b28ed-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b28ed-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b28ed-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b28ed-124">E_NOTIMPL</span></span>|<span data-ttu-id="b28ed-125">Узел не предоставляет реализацию `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="b28ed-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b28ed-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b28ed-126">Remarks</span></span>  
 <span data-ttu-id="b28ed-127">`SetMaxThreads` Среда CLR предоставляет возможность задать максимальное число потоков, доступных для обслуживания запросов на портах ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b28ed-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="b28ed-128">Узлу может потребоваться исключительный контроль над размер пула потоков для реализации, производительности или масштабирования.</span><span class="sxs-lookup"><span data-stu-id="b28ed-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b28ed-129">По этой причине узла не требуется для реализации `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="b28ed-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="b28ed-130">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="b28ed-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28ed-131">Требования</span><span class="sxs-lookup"><span data-stu-id="b28ed-131">Requirements</span></span>  
 <span data-ttu-id="b28ed-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28ed-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28ed-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b28ed-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b28ed-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b28ed-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28ed-135">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28ed-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28ed-136">См. также</span><span class="sxs-lookup"><span data-stu-id="b28ed-136">See Also</span></span>  
 [<span data-ttu-id="b28ed-137">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b28ed-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="b28ed-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b28ed-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
