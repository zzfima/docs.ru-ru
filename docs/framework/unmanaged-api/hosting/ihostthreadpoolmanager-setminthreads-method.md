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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f9852034f6d8208bdaa9b424f689adc374bae2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="0b555-102">Метод IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="0b555-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="0b555-103">Задает минимальное количество свободных потоков, которые должен поддерживать узла обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="0b555-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b555-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b555-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b555-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b555-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="0b555-106">[in] Новый минимальное количество потоков, которые необходимо обслуживать основное приложение.</span><span class="sxs-lookup"><span data-stu-id="0b555-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b555-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b555-107">Return Value</span></span>  
  
|<span data-ttu-id="0b555-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b555-108">HRESULT</span></span>|<span data-ttu-id="0b555-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0b555-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b555-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b555-110">S_OK</span></span>|<span data-ttu-id="0b555-111">`SetMinThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0b555-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="0b555-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b555-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b555-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0b555-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b555-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b555-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b555-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0b555-115">The call timed out.</span></span>|  
|<span data-ttu-id="0b555-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b555-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b555-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0b555-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b555-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b555-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b555-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0b555-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b555-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b555-120">E_FAIL</span></span>|<span data-ttu-id="0b555-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0b555-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b555-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0b555-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b555-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b555-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b555-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0b555-124">E_NOTIMPL</span></span>|<span data-ttu-id="0b555-125">Узел не предоставляет реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="0b555-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b555-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b555-126">Remarks</span></span>  
 <span data-ttu-id="0b555-127">Узел не требуется предоставлять реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="0b555-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="0b555-128">В этом случае он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0b555-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b555-129">Требования</span><span class="sxs-lookup"><span data-stu-id="0b555-129">Requirements</span></span>  
 <span data-ttu-id="0b555-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b555-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b555-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b555-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b555-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b555-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b555-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b555-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b555-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0b555-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="0b555-135">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="0b555-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="0b555-136">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="0b555-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="0b555-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="0b555-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
