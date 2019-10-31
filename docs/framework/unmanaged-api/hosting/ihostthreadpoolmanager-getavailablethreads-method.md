---
title: Метод IHostThreadPoolManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 21449d9365e6260267d3c79f384f6136ce894821
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122097"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="02362-102">Метод IHostThreadPoolManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="02362-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="02362-103">Возвращает число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="02362-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02362-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02362-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02362-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02362-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="02362-106">заполняет Указатель на число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="02362-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02362-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="02362-107">Return Value</span></span>  
  
|<span data-ttu-id="02362-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02362-108">HRESULT</span></span>|<span data-ttu-id="02362-109">Описание</span><span class="sxs-lookup"><span data-stu-id="02362-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02362-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="02362-110">S_OK</span></span>|<span data-ttu-id="02362-111">`GetAvailableThreads` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="02362-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="02362-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02362-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02362-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="02362-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02362-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02362-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02362-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="02362-115">The call timed out.</span></span>|  
|<span data-ttu-id="02362-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02362-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02362-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="02362-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02362-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02362-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02362-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="02362-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02362-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02362-120">E_FAIL</span></span>|<span data-ttu-id="02362-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="02362-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02362-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="02362-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02362-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="02362-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="02362-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="02362-124">E_NOTIMPL</span></span>|<span data-ttu-id="02362-125">Узел не предоставляет реализацию `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="02362-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02362-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="02362-126">Remarks</span></span>  
 <span data-ttu-id="02362-127">Если узел не предоставляет реализацию `GetAvailableThreads`, он должен возвращать значение HRESULT, равное E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="02362-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02362-128">Требования</span><span class="sxs-lookup"><span data-stu-id="02362-128">Requirements</span></span>  
 <span data-ttu-id="02362-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02362-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02362-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="02362-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02362-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="02362-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02362-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02362-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02362-133">См. также</span><span class="sxs-lookup"><span data-stu-id="02362-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="02362-134">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="02362-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
