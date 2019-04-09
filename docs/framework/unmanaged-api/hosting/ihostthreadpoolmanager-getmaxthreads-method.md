---
title: Метод IHostThreadPoolManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dce4efeb82f44e2c0d19e95551696b16e9f07ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157551"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="8da86-102">Метод IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8da86-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="8da86-103">Возвращает максимальное число потоков, ведущий одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="8da86-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8da86-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8da86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8da86-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="8da86-106">[out] Указатель на максимальное число потоков, ведущий в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="8da86-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8da86-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8da86-107">Return Value</span></span>  
  
|<span data-ttu-id="8da86-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8da86-108">HRESULT</span></span>|<span data-ttu-id="8da86-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8da86-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8da86-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8da86-110">S_OK</span></span>|`GetMaxThreads` <span data-ttu-id="8da86-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8da86-111">returned successfully.</span></span>|  
|<span data-ttu-id="8da86-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8da86-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8da86-113">Среда CLR (CLR (не было загружено в процесс, или среда CLR находится в состоянии, в котором она не удается запустить управляемого кода или процесс вызова.</span><span class="sxs-lookup"><span data-stu-id="8da86-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8da86-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8da86-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8da86-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8da86-115">The call timed out.</span></span>|  
|<span data-ttu-id="8da86-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8da86-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8da86-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8da86-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8da86-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8da86-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8da86-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8da86-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8da86-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8da86-120">E_FAIL</span></span>|<span data-ttu-id="8da86-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="8da86-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8da86-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8da86-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8da86-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8da86-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8da86-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8da86-124">E_NOTIMPL</span></span>|<span data-ttu-id="8da86-125">Узел не поддерживает реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="8da86-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8da86-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8da86-126">Remarks</span></span>  
 <span data-ttu-id="8da86-127">Среда CLR вызывает `GetMaxThreads` чтобы определить общее число потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="8da86-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="8da86-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) метод возвращает число потоков, которые в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="8da86-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="8da86-129">Все запросы, превышающие возвращаемым значением `pdwMaxWorkerThreads` параметр остаются в очереди, пока не станут доступными потоков.</span><span class="sxs-lookup"><span data-stu-id="8da86-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="8da86-130">Если узел не поддерживает реализацию `GetMaxThreads`, он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8da86-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8da86-131">Требования</span><span class="sxs-lookup"><span data-stu-id="8da86-131">Requirements</span></span>  
 <span data-ttu-id="8da86-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8da86-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8da86-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8da86-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8da86-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8da86-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8da86-135">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8da86-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8da86-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8da86-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8da86-137">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="8da86-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="8da86-138">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8da86-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="8da86-139">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="8da86-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
