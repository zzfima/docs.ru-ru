---
title: Метод IHostIoCompletionManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faac5adccecdd0aeecede3b4f50a4db554e3d162
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077164"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="a9948-102">Метод IHostIoCompletionManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="a9948-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="a9948-103">Получает минимальное количество потоков, предоставляемых хостом для обработки запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a9948-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9948-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9948-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9948-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9948-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="a9948-106">[out] Указатель на минимальное количество потоков, предоставляемых хостом для обработки операций ввода-вывода запросов.</span><span class="sxs-lookup"><span data-stu-id="a9948-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9948-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a9948-107">Return Value</span></span>  
  
|<span data-ttu-id="a9948-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9948-108">HRESULT</span></span>|<span data-ttu-id="a9948-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a9948-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9948-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9948-110">S_OK</span></span>|<span data-ttu-id="a9948-111">`GetMinThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a9948-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a9948-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9948-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9948-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a9948-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9948-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9948-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9948-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a9948-115">The call timed out.</span></span>|  
|<span data-ttu-id="a9948-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9948-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9948-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a9948-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9948-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9948-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9948-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a9948-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9948-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9948-120">E_FAIL</span></span>|<span data-ttu-id="a9948-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a9948-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9948-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a9948-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9948-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9948-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9948-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a9948-124">E_NOTIMPL</span></span>|<span data-ttu-id="a9948-125">Узел не поддерживает реализацию `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a9948-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9948-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9948-126">Remarks</span></span>  
 <span data-ttu-id="a9948-127">Узлу может потребоваться исключительный контроль над числом потоков, отведенное для обслуживания запросов ввода-вывода, например для реализации, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="a9948-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="a9948-128">По этой причине узел не нужно реализовать `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a9948-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="a9948-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="a9948-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9948-130">Требования</span><span class="sxs-lookup"><span data-stu-id="a9948-130">Requirements</span></span>  
 <span data-ttu-id="a9948-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9948-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9948-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9948-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9948-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9948-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9948-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9948-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9948-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a9948-135">See also</span></span>

- [<span data-ttu-id="a9948-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a9948-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a9948-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a9948-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
