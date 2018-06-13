---
title: Метод IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d68790cdb671efdd0761ceef59196e8646654d5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439612"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="2fc38-102">Метод IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="2fc38-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="2fc38-103">Регистрирует указатель на функцию обратного вызова, основное приложение вызывает для уведомления общеязыковой среды выполнения (CLR) из текущей загруженности памяти компьютера.</span><span class="sxs-lookup"><span data-stu-id="2fc38-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fc38-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fc38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fc38-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="2fc38-106">[in] Указатель интерфейса [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) экземпляре, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="2fc38-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fc38-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2fc38-107">Return Value</span></span>  
  
|<span data-ttu-id="2fc38-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fc38-108">HRESULT</span></span>|<span data-ttu-id="2fc38-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2fc38-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fc38-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fc38-110">S_OK</span></span>|<span data-ttu-id="2fc38-111">`RegisterMemoryNotificationCallback` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2fc38-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="2fc38-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fc38-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fc38-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2fc38-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2fc38-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fc38-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fc38-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2fc38-115">The call timed out.</span></span>|  
|<span data-ttu-id="2fc38-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fc38-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fc38-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2fc38-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fc38-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fc38-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fc38-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2fc38-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fc38-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fc38-120">E_FAIL</span></span>|<span data-ttu-id="2fc38-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="2fc38-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fc38-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2fc38-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fc38-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2fc38-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fc38-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fc38-124">Remarks</span></span>  
 <span data-ttu-id="2fc38-125">Поскольку `ICLRMemoryNotificationCallback` интерфейс определяет только один метод ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), а потому, что `pCallback` является указателем на `ICLRMemoryNotificationCallback` экземпляра, реализованную в среде CLR Регистрация фактически выполняется для самой функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2fc38-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="2fc38-126">Основное приложение вызывает `OnMemoryNotification` условия нехватки памяти отчета, а не с помощью стандартной Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="2fc38-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="2fc38-127">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="2fc38-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fc38-128">Вызовы `OnMemoryNotification` никогда не блокируется.</span><span class="sxs-lookup"><span data-stu-id="2fc38-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="2fc38-129">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="2fc38-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fc38-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2fc38-130">Requirements</span></span>  
 <span data-ttu-id="2fc38-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fc38-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc38-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fc38-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fc38-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fc38-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fc38-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc38-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc38-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc38-135">See Also</span></span>  
 [<span data-ttu-id="2fc38-136">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="2fc38-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="2fc38-137">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="2fc38-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
