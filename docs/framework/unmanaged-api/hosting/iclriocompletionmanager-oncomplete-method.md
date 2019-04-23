---
title: Метод ICLRIoCompletionManager::OnComplete
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d9d4336b79b60e69f980b6d5931e2994732f30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191631"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="dd751-102">Метод ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="dd751-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="dd751-103">Уведомляет общеязыковой среды выполнения (CLR) о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="dd751-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd751-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd751-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd751-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd751-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="dd751-106">[in] Значение HRESULT, указывающее состояние операции привязки.</span><span class="sxs-lookup"><span data-stu-id="dd751-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="dd751-107">Значение S_OK указывает, что операция завершена успешно.</span><span class="sxs-lookup"><span data-stu-id="dd751-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="dd751-108">HOST_E_INTERRUPTED указывает, что вызов прерван до завершения.</span><span class="sxs-lookup"><span data-stu-id="dd751-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="dd751-109">E_FAIL означает, что произошла неизвестная, неустранимого, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="dd751-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="dd751-110">[in] Число байтов, передаваемых во время обработки запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="dd751-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="dd751-111">[in] Указатель на `OVERLAPPED` структуры, который был передан в вызов `IHostIoCompletionManager::Bind` метод.</span><span class="sxs-lookup"><span data-stu-id="dd751-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd751-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd751-112">Return Value</span></span>  
  
|<span data-ttu-id="dd751-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd751-113">HRESULT</span></span>|<span data-ttu-id="dd751-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dd751-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd751-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd751-115">S_OK</span></span>|<span data-ttu-id="dd751-116">`OnComplete` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dd751-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="dd751-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd751-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd751-118">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dd751-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd751-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd751-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd751-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dd751-120">The call timed out.</span></span>|  
|<span data-ttu-id="dd751-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd751-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd751-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dd751-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd751-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd751-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd751-124">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dd751-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd751-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd751-125">E_FAIL</span></span>|<span data-ttu-id="dd751-126">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="dd751-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd751-127">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="dd751-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd751-128">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd751-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd751-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd751-129">Remarks</span></span>  
 <span data-ttu-id="dd751-130">Если узел реализует абстракцию завершения ввода-вывода, среда CLR не дает запросов ввода-вывода через узел с помощью методов класса [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dd751-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="dd751-131">Узел, затем вызывает метод `OnComplete` метод для уведомления среды выполнения о результатах таких запросов.</span><span class="sxs-lookup"><span data-stu-id="dd751-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd751-132">Требования</span><span class="sxs-lookup"><span data-stu-id="dd751-132">Requirements</span></span>  
 <span data-ttu-id="dd751-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd751-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd751-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd751-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd751-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd751-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd751-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd751-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd751-137">См. также</span><span class="sxs-lookup"><span data-stu-id="dd751-137">See also</span></span>

- [<span data-ttu-id="dd751-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="dd751-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="dd751-139">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="dd751-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="dd751-140">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="dd751-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
