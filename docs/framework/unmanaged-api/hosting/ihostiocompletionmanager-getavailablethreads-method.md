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
ms.openlocfilehash: 1e96a12bbf9c4fdc8a0bc79661070eb7fec1a593
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973099"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="18f67-102">Метод IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="18f67-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="18f67-103">Получает количество потоков завершения ввода-вывода, от общего числа потоки, управляемые основного приложения, которые в настоящее время не обслуживает запросы.</span><span class="sxs-lookup"><span data-stu-id="18f67-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f67-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18f67-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="18f67-106">[out] Указатель на число операций ввода-вывода потоков завершения управляет узел, доступных для обслуживания запросов.</span><span class="sxs-lookup"><span data-stu-id="18f67-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18f67-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18f67-107">Return Value</span></span>  
  
|<span data-ttu-id="18f67-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18f67-108">HRESULT</span></span>|<span data-ttu-id="18f67-109">Описание</span><span class="sxs-lookup"><span data-stu-id="18f67-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18f67-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="18f67-110">S_OK</span></span>|<span data-ttu-id="18f67-111">`GetAvailableThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="18f67-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="18f67-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="18f67-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18f67-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="18f67-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18f67-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18f67-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18f67-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="18f67-115">The call timed out.</span></span>|  
|<span data-ttu-id="18f67-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18f67-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18f67-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="18f67-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18f67-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18f67-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18f67-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="18f67-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18f67-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18f67-120">E_FAIL</span></span>|<span data-ttu-id="18f67-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="18f67-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="18f67-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="18f67-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18f67-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="18f67-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="18f67-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="18f67-124">E_NOTIMPL</span></span>|<span data-ttu-id="18f67-125">Узел не поддерживает реализацию `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="18f67-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f67-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="18f67-126">Remarks</span></span>  
 <span data-ttu-id="18f67-127">Узлу может потребоваться исключительный контроль над размер пула потоков завершения ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="18f67-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="18f67-128">Таким образом, узел не нужно реализовать `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="18f67-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="18f67-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="18f67-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f67-130">Требования</span><span class="sxs-lookup"><span data-stu-id="18f67-130">Requirements</span></span>  
 <span data-ttu-id="18f67-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f67-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f67-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="18f67-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18f67-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18f67-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18f67-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f67-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f67-135">См. также</span><span class="sxs-lookup"><span data-stu-id="18f67-135">See also</span></span>

- [<span data-ttu-id="18f67-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="18f67-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="18f67-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="18f67-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
