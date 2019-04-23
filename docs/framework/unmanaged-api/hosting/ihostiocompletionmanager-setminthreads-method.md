---
title: Метод IHostIoCompletionManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fd37546c63ef5e5f25686e105247555dfeb132a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222787"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="f4dd5-102">Метод IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="f4dd5-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="f4dd5-103">Задает минимальное количество потоков, которые основное приложение должно выделить для завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4dd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4dd5-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4dd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4dd5-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="f4dd5-106">[in] Минимальное количество потоков завершения ввода-вывода, которые следует создать узел.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4dd5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4dd5-107">Return Value</span></span>  
  
|<span data-ttu-id="f4dd5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4dd5-108">HRESULT</span></span>|<span data-ttu-id="f4dd5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f4dd5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4dd5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4dd5-110">S_OK</span></span>|<span data-ttu-id="f4dd5-111">`SetMinThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f4dd5-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f4dd5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f4dd5-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f4dd5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f4dd5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f4dd5-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-115">The call timed out.</span></span>|  
|<span data-ttu-id="f4dd5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f4dd5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f4dd5-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f4dd5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f4dd5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f4dd5-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f4dd5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f4dd5-120">E_FAIL</span></span>|<span data-ttu-id="f4dd5-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f4dd5-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f4dd5-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f4dd5-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f4dd5-124">E_NOTIMPL</span></span>|<span data-ttu-id="f4dd5-125">Узел не поддерживает реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4dd5-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4dd5-126">Remarks</span></span>  
 <span data-ttu-id="f4dd5-127">Узлу может потребоваться исключительный контроль над количество потоков, которое может быть выделено для обработки запросов ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="f4dd5-128">По этой причине узел не нужно реализовать `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="f4dd5-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="f4dd5-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4dd5-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f4dd5-130">Requirements</span></span>  
 <span data-ttu-id="f4dd5-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4dd5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4dd5-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4dd5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4dd5-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4dd5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4dd5-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4dd5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dd5-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f4dd5-135">See also</span></span>

- [<span data-ttu-id="f4dd5-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f4dd5-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="f4dd5-137">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="f4dd5-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="f4dd5-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f4dd5-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
