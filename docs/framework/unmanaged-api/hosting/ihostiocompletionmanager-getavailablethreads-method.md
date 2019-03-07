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
ms.openlocfilehash: 27922c1b1b576ae34bfbe363f3d46e10d0f2551c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485178"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="c44fe-102">Метод IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="c44fe-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="c44fe-103">Получает количество потоков завершения ввода-вывода, от общего числа потоки, управляемые основного приложения, которые в настоящее время не обслуживает запросы.</span><span class="sxs-lookup"><span data-stu-id="c44fe-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c44fe-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c44fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c44fe-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="c44fe-106">[out] Указатель на число операций ввода-вывода потоков завершения управляет узел, доступных для обслуживания запросов.</span><span class="sxs-lookup"><span data-stu-id="c44fe-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c44fe-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c44fe-107">Return Value</span></span>  
  
|<span data-ttu-id="c44fe-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c44fe-108">HRESULT</span></span>|<span data-ttu-id="c44fe-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c44fe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c44fe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c44fe-110">S_OK</span></span>|<span data-ttu-id="c44fe-111">`GetAvailableThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c44fe-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c44fe-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c44fe-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c44fe-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c44fe-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c44fe-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c44fe-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c44fe-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c44fe-115">The call timed out.</span></span>|  
|<span data-ttu-id="c44fe-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c44fe-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c44fe-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c44fe-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c44fe-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c44fe-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c44fe-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c44fe-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c44fe-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c44fe-120">E_FAIL</span></span>|<span data-ttu-id="c44fe-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c44fe-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c44fe-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c44fe-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c44fe-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c44fe-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c44fe-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c44fe-124">E_NOTIMPL</span></span>|<span data-ttu-id="c44fe-125">Узел не поддерживает реализацию `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="c44fe-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c44fe-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c44fe-126">Remarks</span></span>  
 <span data-ttu-id="c44fe-127">Узлу может потребоваться исключительный контроль над размер пула потоков завершения ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="c44fe-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="c44fe-128">Таким образом, узел не нужно реализовать `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="c44fe-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="c44fe-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="c44fe-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44fe-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c44fe-130">Requirements</span></span>  
 <span data-ttu-id="c44fe-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44fe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44fe-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c44fe-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c44fe-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c44fe-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c44fe-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44fe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44fe-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c44fe-135">See also</span></span>
- [<span data-ttu-id="c44fe-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c44fe-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c44fe-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c44fe-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
