---
title: Метод IHostThreadPoolManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f978f565dd93eb10a68942fc463f7d5cc212e6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442037"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="11a78-102">Метод IHostThreadPoolManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="11a78-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="11a78-103">Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="11a78-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a78-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11a78-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="11a78-106">Максимальное количество рабочих потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="11a78-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a78-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11a78-107">Return Value</span></span>  
  
|<span data-ttu-id="11a78-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11a78-108">HRESULT</span></span>|<span data-ttu-id="11a78-109">Описание</span><span class="sxs-lookup"><span data-stu-id="11a78-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11a78-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="11a78-110">S_OK</span></span>|<span data-ttu-id="11a78-111">`SetMaxThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="11a78-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="11a78-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11a78-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11a78-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="11a78-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11a78-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11a78-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11a78-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="11a78-115">The call timed out.</span></span>|  
|<span data-ttu-id="11a78-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11a78-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11a78-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="11a78-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11a78-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11a78-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11a78-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="11a78-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11a78-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11a78-120">E_FAIL</span></span>|<span data-ttu-id="11a78-121">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="11a78-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="11a78-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="11a78-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11a78-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="11a78-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="11a78-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="11a78-124">E_NOTIMPL</span></span>|<span data-ttu-id="11a78-125">Узел не предоставляет реализацию `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="11a78-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a78-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="11a78-126">Remarks</span></span>  
 <span data-ttu-id="11a78-127">Узел не является обязательным для предоставления среде CLR для настройки размера пула потоков.</span><span class="sxs-lookup"><span data-stu-id="11a78-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="11a78-128">На некоторых серверах может потребоваться исключительный контроль над пула потоков, для реализации, производительности или масштабирования.</span><span class="sxs-lookup"><span data-stu-id="11a78-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="11a78-129">В этом случае основное приложение должно возвратить HRESULT со значением E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="11a78-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a78-130">Требования</span><span class="sxs-lookup"><span data-stu-id="11a78-130">Requirements</span></span>  
 <span data-ttu-id="11a78-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a78-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a78-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11a78-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11a78-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a78-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11a78-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a78-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a78-135">См. также</span><span class="sxs-lookup"><span data-stu-id="11a78-135">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="11a78-136">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="11a78-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="11a78-137">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="11a78-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="11a78-138">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="11a78-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
