---
title: Метод IHostThreadPoolManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: f2d2665382559596563d9b155d2afa4d99c91ee7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141254"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="3de3d-102">Метод IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="3de3d-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="3de3d-103">Задает минимальное число бездействующих потоков, которые должны поддерживаться узлом в ожидаемых запросах.</span><span class="sxs-lookup"><span data-stu-id="3de3d-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3de3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3de3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3de3d-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="3de3d-106">окне Новое минимальное число потоков, которое должен поддерживать узел.</span><span class="sxs-lookup"><span data-stu-id="3de3d-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3de3d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3de3d-107">Return Value</span></span>  
  
|<span data-ttu-id="3de3d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3de3d-108">HRESULT</span></span>|<span data-ttu-id="3de3d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3de3d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3de3d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3de3d-110">S_OK</span></span>|<span data-ttu-id="3de3d-111">`SetMinThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="3de3d-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3de3d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3de3d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3de3d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3de3d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3de3d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3de3d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3de3d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="3de3d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3de3d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3de3d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3de3d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="3de3d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3de3d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3de3d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3de3d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="3de3d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3de3d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3de3d-120">E_FAIL</span></span>|<span data-ttu-id="3de3d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="3de3d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3de3d-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3de3d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3de3d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3de3d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3de3d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3de3d-124">E_NOTIMPL</span></span>|<span data-ttu-id="3de3d-125">Узел не предоставляет реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="3de3d-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3de3d-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="3de3d-126">Remarks</span></span>  
 <span data-ttu-id="3de3d-127">Узел не требуется для предоставления реализации `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="3de3d-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="3de3d-128">В этом случае он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3de3d-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de3d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3de3d-129">Requirements</span></span>  
 <span data-ttu-id="3de3d-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de3d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de3d-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3de3d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3de3d-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3de3d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3de3d-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de3d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de3d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3de3d-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="3de3d-135">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="3de3d-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="3de3d-136">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3de3d-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="3de3d-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="3de3d-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
