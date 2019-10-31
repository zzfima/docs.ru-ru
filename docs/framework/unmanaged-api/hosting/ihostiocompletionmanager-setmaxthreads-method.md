---
title: Метод IHostIoCompletionManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 7a16c141d9d07af82bd984955e06199e66ce3bbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133765"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="87718-102">Метод IHostIoCompletionManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="87718-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="87718-103">Задает максимальное число потоков, которое узел запрашивает для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="87718-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87718-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87718-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87718-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87718-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="87718-106">окне Максимальное число потоков, которое можно выделить для запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="87718-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87718-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="87718-107">Return Value</span></span>  
  
|<span data-ttu-id="87718-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87718-108">HRESULT</span></span>|<span data-ttu-id="87718-109">Описание</span><span class="sxs-lookup"><span data-stu-id="87718-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87718-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87718-110">S_OK</span></span>|<span data-ttu-id="87718-111">`SetMaxThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="87718-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="87718-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87718-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87718-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="87718-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87718-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87718-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87718-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="87718-115">The call timed out.</span></span>|  
|<span data-ttu-id="87718-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87718-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87718-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="87718-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87718-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87718-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87718-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="87718-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87718-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87718-120">E_FAIL</span></span>|<span data-ttu-id="87718-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="87718-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87718-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="87718-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87718-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87718-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87718-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="87718-124">E_NOTIMPL</span></span>|<span data-ttu-id="87718-125">Узел не предоставляет реализацию `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="87718-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87718-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="87718-126">Remarks</span></span>  
 <span data-ttu-id="87718-127">`SetMaxThreads` предоставляет среде CLR возможность задать максимальное число потоков, доступных для запросов на обслуживание на портах ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="87718-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="87718-128">Узлу может потребоваться эксклюзивный контроль над размером пула потоков по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="87718-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="87718-129">По этой причине узел не требуется для реализации `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="87718-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="87718-130">В этом случае узел должен вернуть значение E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="87718-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87718-131">Требования</span><span class="sxs-lookup"><span data-stu-id="87718-131">Requirements</span></span>  
 <span data-ttu-id="87718-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87718-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87718-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87718-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87718-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="87718-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87718-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87718-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87718-136">См. также</span><span class="sxs-lookup"><span data-stu-id="87718-136">See also</span></span>

- [<span data-ttu-id="87718-137">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87718-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="87718-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87718-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
