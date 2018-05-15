---
title: Метод IHostIoCompletionManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb5de5b46a46d5caa74b83f16d943edc39d08b01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="08c60-102">Метод IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="08c60-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="08c60-103">Возвращает число потоков завершения ввода-вывода, от общего количества потоков, управляемых сервером, которые в настоящее время не обслуживает запросы.</span><span class="sxs-lookup"><span data-stu-id="08c60-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08c60-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08c60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08c60-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="08c60-106">[out] Указатель на число потоков ввода-вывода выполнения управляемых узлом, доступных в настоящее время для обслуживания запросов.</span><span class="sxs-lookup"><span data-stu-id="08c60-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08c60-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08c60-107">Return Value</span></span>  
  
|<span data-ttu-id="08c60-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08c60-108">HRESULT</span></span>|<span data-ttu-id="08c60-109">Описание</span><span class="sxs-lookup"><span data-stu-id="08c60-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08c60-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08c60-110">S_OK</span></span>|<span data-ttu-id="08c60-111">`GetAvailableThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="08c60-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="08c60-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08c60-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08c60-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="08c60-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08c60-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08c60-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08c60-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="08c60-115">The call timed out.</span></span>|  
|<span data-ttu-id="08c60-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08c60-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08c60-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="08c60-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08c60-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08c60-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08c60-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="08c60-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08c60-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08c60-120">E_FAIL</span></span>|<span data-ttu-id="08c60-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="08c60-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08c60-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="08c60-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08c60-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="08c60-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="08c60-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="08c60-124">E_NOTIMPL</span></span>|<span data-ttu-id="08c60-125">Узел не предоставляет реализацию `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="08c60-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c60-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="08c60-126">Remarks</span></span>  
 <span data-ttu-id="08c60-127">Узлу может потребоваться исключительный контроль над размер пула потоков завершения ввода-вывода, для реализации, производительности или масштабирования.</span><span class="sxs-lookup"><span data-stu-id="08c60-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="08c60-128">Таким образом, узел не требуется реализовывать `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="08c60-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="08c60-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="08c60-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c60-130">Требования</span><span class="sxs-lookup"><span data-stu-id="08c60-130">Requirements</span></span>  
 <span data-ttu-id="08c60-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c60-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c60-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08c60-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08c60-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08c60-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08c60-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c60-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c60-135">См. также</span><span class="sxs-lookup"><span data-stu-id="08c60-135">See Also</span></span>  
 [<span data-ttu-id="08c60-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="08c60-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="08c60-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="08c60-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
