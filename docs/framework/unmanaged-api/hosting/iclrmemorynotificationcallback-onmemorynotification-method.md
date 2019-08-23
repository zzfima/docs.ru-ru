---
title: Метод ICLRMemoryNotificationCallback::OnMemoryNotification
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949705"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="0611c-102">Метод ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="0611c-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="0611c-103">Уведомляет среду CLR о загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0611c-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0611c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0611c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0611c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0611c-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="0611c-106">окне Одно из значений [емеморяваилабле](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) , указывающее на нехватку памяти в данный момент на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0611c-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0611c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0611c-107">Return Value</span></span>  
  
|<span data-ttu-id="0611c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0611c-108">HRESULT</span></span>|<span data-ttu-id="0611c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0611c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0611c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0611c-110">S_OK</span></span>|<span data-ttu-id="0611c-111">`OnMemoryNotification`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0611c-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="0611c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0611c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0611c-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0611c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0611c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0611c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0611c-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0611c-115">The call timed out.</span></span>|  
|<span data-ttu-id="0611c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0611c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0611c-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0611c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0611c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0611c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0611c-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0611c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0611c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0611c-120">E_FAIL</span></span>|<span data-ttu-id="0611c-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0611c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0611c-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0611c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0611c-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0611c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0611c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0611c-124">Remarks</span></span>  
 <span data-ttu-id="0611c-125">Среда CLR регистрирует обратный вызов `OnMemoryNotification` с помощью вызова метода [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0611c-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="0611c-126">Среда выполнения использует сведения, возвращаемые при обратном вызове, чтобы освободить дополнительную память, когда узел сообщает, что ресурсы памяти имеют низкий уровень.</span><span class="sxs-lookup"><span data-stu-id="0611c-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0611c-127">`OnMemoryNotification` Вызовы никогда не блокируются.</span><span class="sxs-lookup"><span data-stu-id="0611c-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="0611c-128">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="0611c-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0611c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="0611c-129">Requirements</span></span>  
 <span data-ttu-id="0611c-130">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0611c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0611c-131">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0611c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0611c-132">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0611c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0611c-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0611c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0611c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0611c-134">See also</span></span>

- [<span data-ttu-id="0611c-135">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0611c-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="0611c-136">Метод RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="0611c-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="0611c-137">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="0611c-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
