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
ms.openlocfilehash: d35fd91f2a28c392176a6dd87bd21baa964ee9a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133813"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="84edc-102">Метод IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="84edc-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="84edc-103">Возвращает максимальное число потоков, которое узел может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="84edc-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84edc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84edc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84edc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84edc-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="84edc-106">заполняет Указатель на максимальное количество потоков в пуле потоков, которое узел может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="84edc-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84edc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84edc-107">Return Value</span></span>  
  
|<span data-ttu-id="84edc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84edc-108">HRESULT</span></span>|<span data-ttu-id="84edc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="84edc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84edc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="84edc-110">S_OK</span></span>|<span data-ttu-id="84edc-111">`GetMaxThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="84edc-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="84edc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84edc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84edc-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="84edc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84edc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84edc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84edc-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="84edc-115">The call timed out.</span></span>|  
|<span data-ttu-id="84edc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84edc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84edc-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="84edc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84edc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84edc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84edc-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="84edc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84edc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84edc-120">E_FAIL</span></span>|<span data-ttu-id="84edc-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="84edc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84edc-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="84edc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84edc-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84edc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84edc-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="84edc-124">E_NOTIMPL</span></span>|<span data-ttu-id="84edc-125">Узел не предоставляет реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="84edc-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84edc-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="84edc-126">Remarks</span></span>  
 <span data-ttu-id="84edc-127">Узлу может потребоваться эксклюзивный контроль над количеством потоков, которые могут быть выделены для обработки запросов ввода-вывода, по таким причинам, как реализация, производительность или масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="84edc-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="84edc-128">По этой причине узел не требуется для реализации `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="84edc-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="84edc-129">В этом случае узел должен вернуть значение E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="84edc-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84edc-130">Требования</span><span class="sxs-lookup"><span data-stu-id="84edc-130">Requirements</span></span>  
 <span data-ttu-id="84edc-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84edc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84edc-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84edc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84edc-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84edc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84edc-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84edc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84edc-135">См. также</span><span class="sxs-lookup"><span data-stu-id="84edc-135">See also</span></span>

- [<span data-ttu-id="84edc-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="84edc-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="84edc-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="84edc-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
