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
ms.openlocfilehash: e53265556de026e84af7ca345a5f82be3c5ff812
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122057"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="ace41-102">Метод IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ace41-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="ace41-103">Возвращает максимальное число потоков, которые обслуживается одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ace41-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ace41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ace41-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ace41-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="ace41-106">заполняет Указатель на максимальное число потоков, поддерживаемых узлом в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ace41-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ace41-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ace41-107">Return Value</span></span>  
  
|<span data-ttu-id="ace41-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ace41-108">HRESULT</span></span>|<span data-ttu-id="ace41-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ace41-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ace41-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ace41-110">S_OK</span></span>|<span data-ttu-id="ace41-111">`GetMaxThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ace41-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ace41-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ace41-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ace41-113">Общеязыковая среда выполнения (CLR не загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ace41-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ace41-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ace41-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ace41-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ace41-115">The call timed out.</span></span>|  
|<span data-ttu-id="ace41-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ace41-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ace41-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ace41-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ace41-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ace41-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ace41-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ace41-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ace41-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ace41-120">E_FAIL</span></span>|<span data-ttu-id="ace41-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ace41-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ace41-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ace41-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ace41-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ace41-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ace41-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ace41-124">E_NOTIMPL</span></span>|<span data-ttu-id="ace41-125">Узел не предоставляет реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ace41-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace41-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="ace41-126">Remarks</span></span>  
 <span data-ttu-id="ace41-127">Среда CLR вызывает `GetMaxThreads`, чтобы определить общее число потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="ace41-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="ace41-128">Метод [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) возвращает число потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="ace41-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="ace41-129">Все запросы выше возвращенного значения параметра `pdwMaxWorkerThreads` остаются в очереди до тех пор, пока потоки не станут доступными.</span><span class="sxs-lookup"><span data-stu-id="ace41-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="ace41-130">Если узел не предоставляет реализацию `GetMaxThreads`, он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ace41-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace41-131">Требования</span><span class="sxs-lookup"><span data-stu-id="ace41-131">Requirements</span></span>  
 <span data-ttu-id="ace41-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ace41-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace41-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ace41-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ace41-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ace41-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ace41-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace41-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace41-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ace41-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ace41-137">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="ace41-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="ace41-138">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ace41-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="ace41-139">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ace41-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
