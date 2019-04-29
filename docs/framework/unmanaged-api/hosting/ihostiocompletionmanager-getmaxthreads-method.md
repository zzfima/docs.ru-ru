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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796856"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="df286-102">Метод IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="df286-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="df286-103">Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="df286-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df286-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df286-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df286-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df286-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="df286-106">[out] Указатель на максимальное число потоков в пуле потоков, основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="df286-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df286-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="df286-107">Return Value</span></span>  
  
|<span data-ttu-id="df286-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df286-108">HRESULT</span></span>|<span data-ttu-id="df286-109">Описание</span><span class="sxs-lookup"><span data-stu-id="df286-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df286-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="df286-110">S_OK</span></span>|<span data-ttu-id="df286-111">`GetMaxThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="df286-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="df286-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df286-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df286-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="df286-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df286-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df286-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df286-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="df286-115">The call timed out.</span></span>|  
|<span data-ttu-id="df286-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df286-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df286-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="df286-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df286-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df286-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df286-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="df286-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df286-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df286-120">E_FAIL</span></span>|<span data-ttu-id="df286-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="df286-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df286-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="df286-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df286-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df286-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="df286-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="df286-124">E_NOTIMPL</span></span>|<span data-ttu-id="df286-125">Узел не поддерживает реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="df286-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df286-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="df286-126">Remarks</span></span>  
 <span data-ttu-id="df286-127">Узлу может потребоваться исключительный контроль над количество потоков, которое может быть выделено для обработки запросов ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="df286-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="df286-128">По этой причине узел не нужно реализовать `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="df286-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="df286-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="df286-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df286-130">Требования</span><span class="sxs-lookup"><span data-stu-id="df286-130">Requirements</span></span>  
 <span data-ttu-id="df286-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df286-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df286-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df286-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df286-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df286-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df286-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df286-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df286-135">См. также</span><span class="sxs-lookup"><span data-stu-id="df286-135">See also</span></span>

- [<span data-ttu-id="df286-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="df286-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="df286-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="df286-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
