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
ms.openlocfilehash: 8b1fc936b601d327ce6306f22dbec2c1078718da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133732"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="fd699-102">Метод IHostIoCompletionManager::SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="fd699-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="fd699-103">Задает минимальное число потоков, которое узел должен выделить при завершении ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="fd699-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd699-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd699-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd699-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd699-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="fd699-106">окне Минимальное число потоков завершения ввода-вывода, которые должен создать узел.</span><span class="sxs-lookup"><span data-stu-id="fd699-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd699-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd699-107">Return Value</span></span>  
  
|<span data-ttu-id="fd699-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd699-108">HRESULT</span></span>|<span data-ttu-id="fd699-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd699-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd699-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd699-110">S_OK</span></span>|<span data-ttu-id="fd699-111">`SetMinThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fd699-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fd699-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd699-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd699-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fd699-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd699-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd699-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd699-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fd699-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd699-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd699-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd699-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fd699-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd699-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd699-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd699-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fd699-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd699-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd699-120">E_FAIL</span></span>|<span data-ttu-id="fd699-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fd699-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd699-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fd699-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd699-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd699-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd699-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fd699-124">E_NOTIMPL</span></span>|<span data-ttu-id="fd699-125">Узел не предоставляет реализацию `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="fd699-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd699-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="fd699-126">Remarks</span></span>  
 <span data-ttu-id="fd699-127">Узлу может потребоваться эксклюзивный контроль над количеством потоков, которые могут быть выделены для обработки запросов ввода-вывода, по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="fd699-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="fd699-128">По этой причине узел не требуется для реализации `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="fd699-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="fd699-129">В этом случае узел должен вернуть значение E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="fd699-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd699-130">Требования</span><span class="sxs-lookup"><span data-stu-id="fd699-130">Requirements</span></span>  
 <span data-ttu-id="fd699-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd699-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd699-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd699-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd699-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd699-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd699-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd699-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd699-135">См. также</span><span class="sxs-lookup"><span data-stu-id="fd699-135">See also</span></span>

- [<span data-ttu-id="fd699-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd699-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="fd699-137">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="fd699-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="fd699-138">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd699-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
