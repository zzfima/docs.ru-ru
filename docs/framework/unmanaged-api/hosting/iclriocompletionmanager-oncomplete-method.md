---
title: "Метод ICLRIoCompletionManager::OnComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f933172e9de5aa18d880791c439d51cce919e83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="d9313-102">Метод ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="d9313-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="d9313-103">Сообщает о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова общеязыковой среды выполнения (CLR) [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d9313-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9313-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9313-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9313-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9313-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="d9313-106">[in] Значение HRESULT, указывающее состояние операции привязки.</span><span class="sxs-lookup"><span data-stu-id="d9313-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="d9313-107">Значение S_OK указывает, что операция завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="d9313-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="d9313-108">HOST_E_INTERRUPTED указывает, что вызов прерван до завершения.</span><span class="sxs-lookup"><span data-stu-id="d9313-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="d9313-109">E_FAIL свидетельствует неизвестного, неустранимого, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="d9313-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="d9313-110">[in] Число байтов, передаваемых во время обработки запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="d9313-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="d9313-111">[in] Указатель на `OVERLAPPED` структуры, который был передан в вызов функции `IHostIoCompletionManager::Bind` метод.</span><span class="sxs-lookup"><span data-stu-id="d9313-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9313-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9313-112">Return Value</span></span>  
  
|<span data-ttu-id="d9313-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9313-113">HRESULT</span></span>|<span data-ttu-id="d9313-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d9313-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9313-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9313-115">S_OK</span></span>|<span data-ttu-id="d9313-116">`OnComplete`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d9313-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="d9313-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9313-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9313-118">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d9313-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9313-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9313-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9313-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d9313-120">The call timed out.</span></span>|  
|<span data-ttu-id="d9313-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9313-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9313-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d9313-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9313-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9313-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9313-124">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d9313-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9313-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9313-125">E_FAIL</span></span>|<span data-ttu-id="d9313-126">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9313-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9313-127">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d9313-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9313-128">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d9313-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9313-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9313-129">Remarks</span></span>  
 <span data-ttu-id="d9313-130">Если узел реализует абстракцию завершения ввода-вывода, среда CLR выполняет запросы ввода-вывода через узел с помощью методов [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d9313-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="d9313-131">Затем основное приложение вызывает `OnComplete` метод для уведомления среды выполнения о результатах таких запросов.</span><span class="sxs-lookup"><span data-stu-id="d9313-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9313-132">Требования</span><span class="sxs-lookup"><span data-stu-id="d9313-132">Requirements</span></span>  
 <span data-ttu-id="d9313-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9313-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9313-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9313-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9313-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9313-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9313-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9313-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9313-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d9313-137">See Also</span></span>  
 [<span data-ttu-id="d9313-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d9313-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="d9313-139">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d9313-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="d9313-140">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="d9313-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
