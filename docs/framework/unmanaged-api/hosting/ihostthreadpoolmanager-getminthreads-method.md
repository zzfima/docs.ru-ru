---
title: Метод IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1230a72d06677b4d36d10a8a31d63638c1fcd41
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170697"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="cc605-102">Метод IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="cc605-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="cc605-103">Получает минимальное количество свободных потоков, ведущий в пуле потоков обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="cc605-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc605-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc605-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc605-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc605-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="cc605-106">[out] Указатель на минимальное количество свободных рабочих потоков, которые в данный момент основным приложением.</span><span class="sxs-lookup"><span data-stu-id="cc605-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc605-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc605-107">Return Value</span></span>  
  
|<span data-ttu-id="cc605-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc605-108">HRESULT</span></span>|<span data-ttu-id="cc605-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cc605-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc605-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc605-110">S_OK</span></span>|<span data-ttu-id="cc605-111">`GetMinThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cc605-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cc605-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc605-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc605-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cc605-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc605-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc605-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc605-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cc605-115">The call timed out.</span></span>|  
|<span data-ttu-id="cc605-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc605-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc605-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cc605-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc605-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc605-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc605-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cc605-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc605-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc605-120">E_FAIL</span></span>|<span data-ttu-id="cc605-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="cc605-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc605-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cc605-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc605-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cc605-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cc605-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cc605-124">E_NOTIMPL</span></span>|<span data-ttu-id="cc605-125">Узел не поддерживает реализацию `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cc605-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc605-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc605-126">Remarks</span></span>  
 <span data-ttu-id="cc605-127">Узел не требуется предоставлять реализацию метода `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cc605-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="cc605-128">В этом случае он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="cc605-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc605-129">Требования</span><span class="sxs-lookup"><span data-stu-id="cc605-129">Requirements</span></span>  
 <span data-ttu-id="cc605-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc605-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc605-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc605-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc605-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc605-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc605-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc605-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc605-134">См. также</span><span class="sxs-lookup"><span data-stu-id="cc605-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="cc605-135">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="cc605-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="cc605-136">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="cc605-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="cc605-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="cc605-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
