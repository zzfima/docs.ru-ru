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
ms.openlocfilehash: 2fa429979faa04518397cf58aaa62d3e45230a76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133836"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="94f9d-102">Метод IHostIoCompletionManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="94f9d-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="94f9d-103">Возвращает количество потоков завершения ввода-вывода из общего числа потоков, управляемых узлом, которые в настоящее время не обслуживают запросы.</span><span class="sxs-lookup"><span data-stu-id="94f9d-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94f9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94f9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94f9d-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="94f9d-106">заполняет Указатель на число потоков завершения ввода-вывода, управляемых узлом, которые в настоящее время доступны для запросов на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="94f9d-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94f9d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="94f9d-107">Return Value</span></span>  
  
|<span data-ttu-id="94f9d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94f9d-108">HRESULT</span></span>|<span data-ttu-id="94f9d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="94f9d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94f9d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="94f9d-110">S_OK</span></span>|<span data-ttu-id="94f9d-111">`GetAvailableThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="94f9d-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="94f9d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94f9d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94f9d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="94f9d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94f9d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94f9d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94f9d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="94f9d-115">The call timed out.</span></span>|  
|<span data-ttu-id="94f9d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94f9d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94f9d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="94f9d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94f9d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94f9d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94f9d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="94f9d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94f9d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94f9d-120">E_FAIL</span></span>|<span data-ttu-id="94f9d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="94f9d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94f9d-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="94f9d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94f9d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94f9d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="94f9d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="94f9d-124">E_NOTIMPL</span></span>|<span data-ttu-id="94f9d-125">Узел не предоставляет реализацию `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="94f9d-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94f9d-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="94f9d-126">Remarks</span></span>  
 <span data-ttu-id="94f9d-127">Ведущему приложению может потребоваться монопольный контроль над размером пула потоков завершения ввода-вывода по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="94f9d-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="94f9d-128">Поэтому узел не требуется для реализации `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="94f9d-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="94f9d-129">В этом случае узел должен вернуть значение E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="94f9d-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94f9d-130">Требования</span><span class="sxs-lookup"><span data-stu-id="94f9d-130">Requirements</span></span>  
 <span data-ttu-id="94f9d-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94f9d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f9d-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94f9d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94f9d-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94f9d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94f9d-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f9d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f9d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="94f9d-135">See also</span></span>

- [<span data-ttu-id="94f9d-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="94f9d-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="94f9d-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="94f9d-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
