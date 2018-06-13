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
ms.openlocfilehash: 8544466edcaca1198d7a7ca92a3f9b9a16847193
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442489"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="cc791-102">Метод IHostIoCompletionManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="cc791-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="cc791-103">Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="cc791-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc791-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc791-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc791-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc791-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="cc791-106">[out] Указатель на максимальное число потоков в пуле потоков, основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="cc791-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc791-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc791-107">Return Value</span></span>  
  
|<span data-ttu-id="cc791-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc791-108">HRESULT</span></span>|<span data-ttu-id="cc791-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cc791-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc791-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc791-110">S_OK</span></span>|<span data-ttu-id="cc791-111">`GetMaxThreads` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cc791-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cc791-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc791-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc791-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cc791-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc791-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc791-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc791-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cc791-115">The call timed out.</span></span>|  
|<span data-ttu-id="cc791-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc791-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc791-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cc791-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc791-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc791-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc791-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cc791-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc791-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc791-120">E_FAIL</span></span>|<span data-ttu-id="cc791-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="cc791-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc791-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cc791-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc791-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cc791-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cc791-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cc791-124">E_NOTIMPL</span></span>|<span data-ttu-id="cc791-125">Узел не предоставляет реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="cc791-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc791-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc791-126">Remarks</span></span>  
 <span data-ttu-id="cc791-127">Узлу может потребоваться исключительный контроль над число потоков, которое может быть выделено для обработки запросов ввода-вывода, по причинам реализация, производительность и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="cc791-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="cc791-128">По этой причине узла не требуется для реализации `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="cc791-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="cc791-129">В этом случае узел должен возвращать E_NOTIMPL из этого метода.</span><span class="sxs-lookup"><span data-stu-id="cc791-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc791-130">Требования</span><span class="sxs-lookup"><span data-stu-id="cc791-130">Requirements</span></span>  
 <span data-ttu-id="cc791-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc791-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc791-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc791-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc791-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc791-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc791-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc791-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc791-135">См. также</span><span class="sxs-lookup"><span data-stu-id="cc791-135">See Also</span></span>  
 [<span data-ttu-id="cc791-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cc791-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="cc791-137">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cc791-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
