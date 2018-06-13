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
ms.openlocfilehash: c11fa66ed583df93accc8ff1e5e95164d4de659d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434458"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="a0363-102">Метод ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="a0363-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="a0363-103">Сообщает о состоянии запроса ввода-вывода, которые были выполнены с помощью вызова общеязыковой среды выполнения (CLR) [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a0363-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0363-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0363-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0363-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0363-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="a0363-106">[in] Значение HRESULT, указывающее состояние операции привязки.</span><span class="sxs-lookup"><span data-stu-id="a0363-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="a0363-107">Значение S_OK указывает, что операция завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="a0363-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="a0363-108">HOST_E_INTERRUPTED указывает, что вызов прерван до завершения.</span><span class="sxs-lookup"><span data-stu-id="a0363-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="a0363-109">E_FAIL свидетельствует неизвестного, неустранимого, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="a0363-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="a0363-110">[in] Число байтов, передаваемых во время обработки запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a0363-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="a0363-111">[in] Указатель на `OVERLAPPED` структуры, который был передан в вызов функции `IHostIoCompletionManager::Bind` метод.</span><span class="sxs-lookup"><span data-stu-id="a0363-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0363-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0363-112">Return Value</span></span>  
  
|<span data-ttu-id="a0363-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0363-113">HRESULT</span></span>|<span data-ttu-id="a0363-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a0363-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0363-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0363-115">S_OK</span></span>|<span data-ttu-id="a0363-116">`OnComplete` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a0363-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="a0363-117">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0363-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0363-118">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0363-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0363-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0363-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0363-120">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a0363-120">The call timed out.</span></span>|  
|<span data-ttu-id="a0363-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0363-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0363-122">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a0363-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0363-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0363-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0363-124">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a0363-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0363-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0363-125">E_FAIL</span></span>|<span data-ttu-id="a0363-126">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0363-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0363-127">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0363-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0363-128">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0363-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0363-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0363-129">Remarks</span></span>  
 <span data-ttu-id="a0363-130">Если узел реализует абстракцию завершения ввода-вывода, среда CLR выполняет запросы ввода-вывода через узел с помощью методов [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a0363-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="a0363-131">Затем основное приложение вызывает `OnComplete` метод для уведомления среды выполнения о результатах таких запросов.</span><span class="sxs-lookup"><span data-stu-id="a0363-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0363-132">Требования</span><span class="sxs-lookup"><span data-stu-id="a0363-132">Requirements</span></span>  
 <span data-ttu-id="a0363-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0363-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0363-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0363-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0363-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0363-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0363-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0363-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0363-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a0363-137">See Also</span></span>  
 [<span data-ttu-id="a0363-138">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a0363-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="a0363-139">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a0363-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="a0363-140">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a0363-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
