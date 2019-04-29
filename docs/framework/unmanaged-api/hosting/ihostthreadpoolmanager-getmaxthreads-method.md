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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961217"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="e9a27-102">Метод IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e9a27-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="e9a27-103">Возвращает максимальное число потоков, ведущий одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="e9a27-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9a27-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9a27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9a27-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="e9a27-106">[out] Указатель на максимальное число потоков, ведущий в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="e9a27-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9a27-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e9a27-107">Return Value</span></span>  
  
|<span data-ttu-id="e9a27-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9a27-108">HRESULT</span></span>|<span data-ttu-id="e9a27-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e9a27-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9a27-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9a27-110">S_OK</span></span>|<span data-ttu-id="e9a27-111">`GetMaxThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e9a27-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e9a27-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9a27-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9a27-113">Среда CLR (CLR (не было загружено в процесс, или среда CLR находится в состоянии, в котором она не удается запустить управляемого кода или процесс вызова.</span><span class="sxs-lookup"><span data-stu-id="e9a27-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9a27-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9a27-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9a27-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e9a27-115">The call timed out.</span></span>|  
|<span data-ttu-id="e9a27-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9a27-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9a27-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e9a27-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9a27-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9a27-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9a27-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e9a27-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9a27-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9a27-120">E_FAIL</span></span>|<span data-ttu-id="e9a27-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e9a27-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9a27-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e9a27-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9a27-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e9a27-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e9a27-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e9a27-124">E_NOTIMPL</span></span>|<span data-ttu-id="e9a27-125">Узел не поддерживает реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="e9a27-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a27-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9a27-126">Remarks</span></span>  
 <span data-ttu-id="e9a27-127">Среда CLR вызывает `GetMaxThreads` чтобы определить общее число потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="e9a27-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="e9a27-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) метод возвращает число потоков, которые в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="e9a27-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="e9a27-129">Все запросы, превышающие возвращаемым значением `pdwMaxWorkerThreads` параметр остаются в очереди, пока не станут доступными потоков.</span><span class="sxs-lookup"><span data-stu-id="e9a27-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="e9a27-130">Если узел не поддерживает реализацию `GetMaxThreads`, он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e9a27-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9a27-131">Требования</span><span class="sxs-lookup"><span data-stu-id="e9a27-131">Requirements</span></span>  
 <span data-ttu-id="e9a27-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a27-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a27-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9a27-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9a27-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9a27-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9a27-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a27-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a27-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e9a27-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e9a27-137">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e9a27-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="e9a27-138">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e9a27-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="e9a27-139">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="e9a27-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
