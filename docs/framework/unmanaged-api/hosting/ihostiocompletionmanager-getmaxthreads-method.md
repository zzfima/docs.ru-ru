---
title: Метод IHostIoCompletionManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8875fb24512ddfea57d5f9249e58de3c12b8c507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119168"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="5472e-102">Метод IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="5472e-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="5472e-103">Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="5472e-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5472e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5472e-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5472e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5472e-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="5472e-106">[out] Указатель на максимальное число потоков в пуле потоков, основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="5472e-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5472e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5472e-107">Return Value</span></span>  
  
|<span data-ttu-id="5472e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5472e-108">HRESULT</span></span>|<span data-ttu-id="5472e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5472e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5472e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5472e-110">S_OK</span></span>|`GetMaxThreads` <span data-ttu-id="5472e-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5472e-111">returned successfully.</span></span>|  
|<span data-ttu-id="5472e-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5472e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5472e-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5472e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5472e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5472e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5472e-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5472e-115">The call timed out.</span></span>|  
|<span data-ttu-id="5472e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5472e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5472e-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5472e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5472e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5472e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5472e-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5472e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5472e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5472e-120">E_FAIL</span></span>|<span data-ttu-id="5472e-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="5472e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5472e-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5472e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5472e-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5472e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5472e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5472e-124">E_NOTIMPL</span></span>|<span data-ttu-id="5472e-125">Узел не поддерживает реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="5472e-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5472e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5472e-126">Remarks</span></span>  
 <span data-ttu-id="5472e-127">Узлу может потребоваться исключительный контроль над количество потоков, которое может быть выделено для обработки запросов ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="5472e-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="5472e-128">По этой причине узел не нужно реализовать `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="5472e-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="5472e-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="5472e-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5472e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5472e-130">Requirements</span></span>  
 <span data-ttu-id="5472e-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5472e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5472e-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5472e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5472e-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5472e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5472e-134">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5472e-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5472e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5472e-135">See also</span></span>

- [<span data-ttu-id="5472e-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="5472e-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5472e-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="5472e-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
