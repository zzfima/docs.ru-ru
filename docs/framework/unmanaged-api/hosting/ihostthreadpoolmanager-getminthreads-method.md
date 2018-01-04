---
title: "Метод IHostThreadPoolManager::GetMinThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 393400c7a5d9d4d99431cbea4a3c3c82064218f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="df97c-102">Метод IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="df97c-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="df97c-103">Получает минимальное количество свободных потоков, поддерживаемых основным приложением в пуле потоков обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="df97c-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df97c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df97c-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df97c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df97c-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="df97c-106">[out] Указатель на минимальное количество свободных рабочих потоков, которые в данный момент основным приложением.</span><span class="sxs-lookup"><span data-stu-id="df97c-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df97c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df97c-107">Return Value</span></span>  
  
|<span data-ttu-id="df97c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df97c-108">HRESULT</span></span>|<span data-ttu-id="df97c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="df97c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df97c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="df97c-110">S_OK</span></span>|<span data-ttu-id="df97c-111">`GetMinThreads`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="df97c-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="df97c-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df97c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df97c-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="df97c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df97c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df97c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df97c-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="df97c-115">The call timed out.</span></span>|  
|<span data-ttu-id="df97c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df97c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df97c-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="df97c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df97c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df97c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df97c-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="df97c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df97c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df97c-120">E_FAIL</span></span>|<span data-ttu-id="df97c-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="df97c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df97c-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="df97c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df97c-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df97c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="df97c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="df97c-124">E_NOTIMPL</span></span>|<span data-ttu-id="df97c-125">Узел не предоставляет реализацию `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="df97c-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df97c-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="df97c-126">Remarks</span></span>  
 <span data-ttu-id="df97c-127">Узел не требуется предоставлять реализацию `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="df97c-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="df97c-128">В этом случае он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="df97c-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df97c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="df97c-129">Requirements</span></span>  
 <span data-ttu-id="df97c-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df97c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df97c-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df97c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df97c-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df97c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df97c-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df97c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df97c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="df97c-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="df97c-135">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="df97c-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="df97c-136">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="df97c-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="df97c-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="df97c-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
