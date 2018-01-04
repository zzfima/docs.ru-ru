---
title: "Метод ICLRMemoryNotificationCallback::OnMemoryNotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMemoryNotificationCallback.OnMemoryNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 651dcd6380702a392d2dd06cf899ea567b004ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="c6e9a-102">Метод ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="c6e9a-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="c6e9a-103">Уведомляет общеязыковой среды выполнения (CLR) загрузки памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6e9a-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6e9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6e9a-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="c6e9a-106">[in] Один из [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) значений, указывающее, нехватки памяти компьютера в данный момент возникла.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6e9a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6e9a-107">Return Value</span></span>  
  
|<span data-ttu-id="c6e9a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6e9a-108">HRESULT</span></span>|<span data-ttu-id="c6e9a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c6e9a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6e9a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6e9a-110">S_OK</span></span>|<span data-ttu-id="c6e9a-111">`OnMemoryNotification`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="c6e9a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6e9a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6e9a-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6e9a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6e9a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6e9a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-115">The call timed out.</span></span>|  
|<span data-ttu-id="c6e9a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6e9a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6e9a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6e9a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6e9a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6e9a-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6e9a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6e9a-120">E_FAIL</span></span>|<span data-ttu-id="c6e9a-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6e9a-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6e9a-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6e9a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6e9a-124">Remarks</span></span>  
 <span data-ttu-id="c6e9a-125">Среда CLR регистрирует обратный вызов `OnMemoryNotification` с помощью вызова [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="c6e9a-126">Среда выполнения использует сведения, возвращаемые в обратный вызов, чтобы освободить память, когда узел сообщает, что недостаточно ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6e9a-127">Вызовы `OnMemoryNotification` никогда не блокируется.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="c6e9a-128">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="c6e9a-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6e9a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="c6e9a-129">Requirements</span></span>  
 <span data-ttu-id="c6e9a-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6e9a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6e9a-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6e9a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6e9a-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6e9a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6e9a-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6e9a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e9a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c6e9a-134">See Also</span></span>  
 [<span data-ttu-id="c6e9a-135">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c6e9a-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="c6e9a-136">Метод RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="c6e9a-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="c6e9a-137">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="c6e9a-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
