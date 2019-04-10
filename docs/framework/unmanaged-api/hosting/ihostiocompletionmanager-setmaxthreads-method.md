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
ms.openlocfilehash: 345c7b88b6967773a185538943591383a686748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224127"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="e0f46-102">Метод IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e0f46-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="e0f46-103">Задает максимальное количество потоков, выделяемых основным приложением для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e0f46-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0f46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0f46-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0f46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0f46-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="e0f46-106">[in] Максимальное число потоков в сторону для запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e0f46-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0f46-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0f46-107">Return Value</span></span>  
  
|<span data-ttu-id="e0f46-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0f46-108">HRESULT</span></span>|<span data-ttu-id="e0f46-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e0f46-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0f46-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0f46-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="e0f46-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e0f46-111">returned successfully.</span></span>|  
|<span data-ttu-id="e0f46-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0f46-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0f46-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e0f46-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0f46-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0f46-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0f46-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e0f46-115">The call timed out.</span></span>|  
|<span data-ttu-id="e0f46-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0f46-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0f46-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e0f46-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0f46-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0f46-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0f46-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e0f46-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0f46-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0f46-120">E_FAIL</span></span>|<span data-ttu-id="e0f46-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e0f46-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0f46-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e0f46-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0f46-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0f46-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e0f46-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e0f46-124">E_NOTIMPL</span></span>|<span data-ttu-id="e0f46-125">Узел не поддерживает реализацию `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="e0f46-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0f46-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0f46-126">Remarks</span></span>  
 `SetMaxThreads` <span data-ttu-id="e0f46-127">Среда CLR предоставляет пользователям возможность задать максимальное число потоков, доступных для обслуживания запросов на портов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e0f46-127">provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="e0f46-128">Узлу может потребоваться исключительный контроль над размер пула потоков, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="e0f46-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e0f46-129">По этой причине узел не нужно реализовать `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="e0f46-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="e0f46-130">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="e0f46-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0f46-131">Требования</span><span class="sxs-lookup"><span data-stu-id="e0f46-131">Requirements</span></span>  
 <span data-ttu-id="e0f46-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f46-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f46-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0f46-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0f46-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0f46-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e0f46-135">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0f46-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0f46-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e0f46-136">See also</span></span>

- [<span data-ttu-id="e0f46-137">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="e0f46-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="e0f46-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="e0f46-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
