---
title: "Метод IHostMemoryManager::RegisterMemoryNotificationCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.RegisterMemoryNotificationCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 142fd6edba9a517f0d43db9d070a47ebeba8d313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="2ddc2-102">Метод IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="2ddc2-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="2ddc2-103">Регистрирует указатель на функцию обратного вызова, основное приложение вызывает для уведомления общеязыковой среды выполнения (CLR) из текущей загруженности памяти компьютера.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ddc2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ddc2-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ddc2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ddc2-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="2ddc2-106">[in] Указатель интерфейса [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) экземпляре, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ddc2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ddc2-107">Return Value</span></span>  
  
|<span data-ttu-id="2ddc2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ddc2-108">HRESULT</span></span>|<span data-ttu-id="2ddc2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2ddc2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ddc2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ddc2-110">S_OK</span></span>|<span data-ttu-id="2ddc2-111">`RegisterMemoryNotificationCallback`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="2ddc2-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ddc2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ddc2-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ddc2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ddc2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ddc2-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ddc2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ddc2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ddc2-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ddc2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ddc2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ddc2-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ddc2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ddc2-120">E_FAIL</span></span>|<span data-ttu-id="2ddc2-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ddc2-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ddc2-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ddc2-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ddc2-124">Remarks</span></span>  
 <span data-ttu-id="2ddc2-125">Поскольку `ICLRMemoryNotificationCallback` интерфейс определяет только один метод ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), а потому, что `pCallback` является указателем на `ICLRMemoryNotificationCallback` экземпляра, реализованную в среде CLR Регистрация фактически выполняется для самой функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="2ddc2-126">Основное приложение вызывает `OnMemoryNotification` условия нехватки памяти отчета, а не с помощью стандартной Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="2ddc2-127">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ddc2-128">Вызовы `OnMemoryNotification` никогда не блокируется.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="2ddc2-129">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ddc2-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2ddc2-130">Requirements</span></span>  
 <span data-ttu-id="2ddc2-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ddc2-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ddc2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ddc2-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ddc2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ddc2-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ddc2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddc2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ddc2-135">See Also</span></span>  
 [<span data-ttu-id="2ddc2-136">Iclrmemorynotificationcallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2ddc2-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="2ddc2-137">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2ddc2-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
