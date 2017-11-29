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
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="99a98-102">Метод ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="99a98-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="99a98-103">Сообщает о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова общеязыковой среды выполнения (CLR) [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="99a98-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a98-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99a98-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99a98-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99a98-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="99a98-106">[in] Значение HRESULT, указывающее состояние операции привязки.</span><span class="sxs-lookup"><span data-stu-id="99a98-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="99a98-107">Значение S_OK указывает, что операция завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="99a98-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="99a98-108">HOST_E_INTERRUPTED указывает, что вызов прерван до завершения.</span><span class="sxs-lookup"><span data-stu-id="99a98-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="99a98-109">E_FAIL свидетельствует неизвестного, неустранимого, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="99a98-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="99a98-110">[in] Число байтов, передаваемых во время обработки запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="99a98-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="99a98-111">[in] Указатель на `OVERLAPPED` структуры, который был передан в вызов функции `IHostIoCompletionManager::Bind` метод.</span><span class="sxs-lookup"><span data-stu-id="99a98-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99a98-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99a98-112">Return Value</span></span>  
  
|<span data-ttu-id="99a98-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99a98-113">HRESULT</span></span>|<span data-ttu-id="99a98-114">Описание</span><span class="sxs-lookup"><span data-stu-id="99a98-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99a98-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="99a98-115">S_OK</span></span>|<span data-ttu-id="99a98-116">`OnComplete`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="99a98-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="99a98-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99a98-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99a98-118">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="99a98-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99a98-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99a98-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99a98-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="99a98-120">The call timed out.</span></span>|  
|<span data-ttu-id="99a98-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99a98-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99a98-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="99a98-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99a98-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99a98-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99a98-124">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="99a98-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99a98-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99a98-125">E_FAIL</span></span>|<span data-ttu-id="99a98-126">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="99a98-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99a98-127">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="99a98-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99a98-128">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="99a98-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99a98-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="99a98-129">Remarks</span></span>  
 <span data-ttu-id="99a98-130">Если узел реализует абстракцию завершения ввода-вывода, среда CLR выполняет запросы ввода-вывода через узел с помощью методов [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="99a98-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="99a98-131">Затем основное приложение вызывает `OnComplete` метод для уведомления среды выполнения о результатах таких запросов.</span><span class="sxs-lookup"><span data-stu-id="99a98-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99a98-132">Требования</span><span class="sxs-lookup"><span data-stu-id="99a98-132">Requirements</span></span>  
 <span data-ttu-id="99a98-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99a98-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99a98-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99a98-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99a98-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99a98-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99a98-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99a98-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a98-137">См. также</span><span class="sxs-lookup"><span data-stu-id="99a98-137">See Also</span></span>  
 [<span data-ttu-id="99a98-138">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="99a98-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="99a98-139">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="99a98-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="99a98-140">IHostThreadPoolManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="99a98-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
