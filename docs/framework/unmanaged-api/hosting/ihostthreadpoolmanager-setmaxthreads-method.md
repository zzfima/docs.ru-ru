---
title: "Метод IHostThreadPoolManager::SetMaxThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69465029deb1db191c28313fb9a260d3c5ba5289
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="3eb3a-102">Метод IHostThreadPoolManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3eb3a-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="3eb3a-103">Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eb3a-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3eb3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eb3a-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="3eb3a-106">Максимальное количество рабочих потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eb3a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3eb3a-107">Return Value</span></span>  
  
|<span data-ttu-id="3eb3a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eb3a-108">HRESULT</span></span>|<span data-ttu-id="3eb3a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3eb3a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eb3a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eb3a-110">S_OK</span></span>|<span data-ttu-id="3eb3a-111">`SetMaxThreads`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3eb3a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3eb3a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3eb3a-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3eb3a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3eb3a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3eb3a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-115">The call timed out.</span></span>|  
|<span data-ttu-id="3eb3a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3eb3a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3eb3a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3eb3a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3eb3a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3eb3a-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3eb3a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3eb3a-120">E_FAIL</span></span>|<span data-ttu-id="3eb3a-121">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3eb3a-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3eb3a-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3eb3a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3eb3a-124">E_NOTIMPL</span></span>|<span data-ttu-id="3eb3a-125">Узел не предоставляет реализацию `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eb3a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eb3a-126">Remarks</span></span>  
 <span data-ttu-id="3eb3a-127">Узел не является обязательным для предоставления среде CLR для настройки размера пула потоков.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="3eb3a-128">На некоторых серверах может потребоваться исключительный контроль над пула потоков, для реализации, производительности или масштабирования.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3eb3a-129">В этом случае основное приложение должно возвратить HRESULT со значением E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb3a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3eb3a-130">Requirements</span></span>  
 <span data-ttu-id="3eb3a-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb3a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb3a-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3eb3a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3eb3a-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3eb3a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eb3a-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb3a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb3a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb3a-135">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="3eb3a-136">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3eb3a-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="3eb3a-137">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="3eb3a-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="3eb3a-138">IHostThreadPoolManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3eb3a-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
