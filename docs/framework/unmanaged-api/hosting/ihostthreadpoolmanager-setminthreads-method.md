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
ms.openlocfilehash: 3c79f18c1deec4183a5a736c5acf88e9a1fd8021
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749095"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="c044b-102">Метод IHostThreadPoolManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c044b-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="c044b-103">Задает минимальное количество свободных потоков, которые необходимо поддерживать узел обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="c044b-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c044b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c044b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c044b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c044b-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="c044b-106">[in] Новый минимальное число потоков, которые необходимо поддерживать узла.</span><span class="sxs-lookup"><span data-stu-id="c044b-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c044b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c044b-107">Return Value</span></span>  
  
|<span data-ttu-id="c044b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c044b-108">HRESULT</span></span>|<span data-ttu-id="c044b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c044b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c044b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c044b-110">S_OK</span></span>|<span data-ttu-id="c044b-111">`SetMinThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c044b-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c044b-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c044b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c044b-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c044b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c044b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c044b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c044b-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c044b-115">The call timed out.</span></span>|  
|<span data-ttu-id="c044b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c044b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c044b-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c044b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c044b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c044b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c044b-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c044b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c044b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c044b-120">E_FAIL</span></span>|<span data-ttu-id="c044b-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c044b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c044b-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c044b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c044b-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c044b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c044b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c044b-124">E_NOTIMPL</span></span>|<span data-ttu-id="c044b-125">Узел не поддерживает реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c044b-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c044b-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c044b-126">Remarks</span></span>  
 <span data-ttu-id="c044b-127">Узел не требуется предоставлять реализацию метода `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c044b-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="c044b-128">В этом случае он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c044b-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c044b-129">Требования</span><span class="sxs-lookup"><span data-stu-id="c044b-129">Requirements</span></span>  
 <span data-ttu-id="c044b-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c044b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c044b-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c044b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c044b-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c044b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c044b-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c044b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c044b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c044b-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c044b-135">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c044b-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="c044b-136">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c044b-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="c044b-137">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c044b-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
