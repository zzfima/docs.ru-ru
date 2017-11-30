---
title: "Метод IHostIoCompletionManager::SetMinThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a8903aa2f2119ad3c4dceebfaba9ede26200e899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="8068f-102">Метод IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="8068f-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="8068f-103">Задает минимальное количество потоков, которые основное приложение должно выделить для завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8068f-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8068f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8068f-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8068f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8068f-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="8068f-106">[in] Минимальное количество потоков завершения ввода-вывода, создаваемые узла.</span><span class="sxs-lookup"><span data-stu-id="8068f-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8068f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8068f-107">Return Value</span></span>  
  
|<span data-ttu-id="8068f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8068f-108">HRESULT</span></span>|<span data-ttu-id="8068f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8068f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8068f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8068f-110">S_OK</span></span>|<span data-ttu-id="8068f-111">`SetMinThreads`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8068f-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8068f-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8068f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8068f-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8068f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8068f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8068f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8068f-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8068f-115">The call timed out.</span></span>|  
|<span data-ttu-id="8068f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8068f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8068f-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8068f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8068f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8068f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8068f-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8068f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8068f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8068f-120">E_FAIL</span></span>|<span data-ttu-id="8068f-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8068f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8068f-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8068f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8068f-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8068f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8068f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8068f-124">E_NOTIMPL</span></span>|<span data-ttu-id="8068f-125">Узел не предоставляет реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="8068f-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8068f-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8068f-126">Remarks</span></span>  
 <span data-ttu-id="8068f-127">Узлу может потребоваться исключительный контроль над число потоков, которое может быть выделено для обработки запросов ввода-вывода, по причинам реализация, производительность и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="8068f-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="8068f-128">По этой причине узла не требуется для реализации `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="8068f-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="8068f-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="8068f-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8068f-130">Требования</span><span class="sxs-lookup"><span data-stu-id="8068f-130">Requirements</span></span>  
 <span data-ttu-id="8068f-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8068f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8068f-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8068f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8068f-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8068f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8068f-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8068f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8068f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8068f-135">See Also</span></span>  
 [<span data-ttu-id="8068f-136">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8068f-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="8068f-137">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8068f-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="8068f-138">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8068f-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
