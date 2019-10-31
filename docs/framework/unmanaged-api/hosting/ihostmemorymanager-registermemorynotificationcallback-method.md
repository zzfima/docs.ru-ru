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
ms.openlocfilehash: 4400fab27ed82e540230ce4196844285e8e37d16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128637"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="603ff-102">Метод IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="603ff-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="603ff-103">Регистрирует указатель на функцию обратного вызова, которую вызывает хост для уведомления среды CLR о текущей загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="603ff-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="603ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="603ff-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="603ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="603ff-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="603ff-106">окне Указатель интерфейса на экземпляр [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) , РЕАЛИЗОВАНный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="603ff-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="603ff-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="603ff-107">Return Value</span></span>  
  
|<span data-ttu-id="603ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="603ff-108">HRESULT</span></span>|<span data-ttu-id="603ff-109">Описание</span><span class="sxs-lookup"><span data-stu-id="603ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="603ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="603ff-110">S_OK</span></span>|<span data-ttu-id="603ff-111">`RegisterMemoryNotificationCallback` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="603ff-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="603ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="603ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="603ff-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="603ff-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="603ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="603ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="603ff-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="603ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="603ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="603ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="603ff-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="603ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="603ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="603ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="603ff-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="603ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="603ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="603ff-120">E_FAIL</span></span>|<span data-ttu-id="603ff-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="603ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="603ff-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="603ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="603ff-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="603ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="603ff-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="603ff-124">Remarks</span></span>  
 <span data-ttu-id="603ff-125">Поскольку интерфейс `ICLRMemoryNotificationCallback` определяет только один метод ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), а `pCallback` является указателем на экземпляр `ICLRMemoryNotificationCallback`, ПРЕДОСТАВЛЯЕМый средой CLR, регистрация фактически осуществляется для обратного вызова. сама функция.</span><span class="sxs-lookup"><span data-stu-id="603ff-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="603ff-126">Узел вызывает `OnMemoryNotification`, чтобы сообщить об условиях нехватки памяти, а не использовать стандартную функцию Win32 `CreateMemoryResourceNotification`.</span><span class="sxs-lookup"><span data-stu-id="603ff-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="603ff-127">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="603ff-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="603ff-128">Вызовы `OnMemoryNotification` никогда не блокируются.</span><span class="sxs-lookup"><span data-stu-id="603ff-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="603ff-129">Они всегда возвращают немедленно.</span><span class="sxs-lookup"><span data-stu-id="603ff-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="603ff-130">Требования</span><span class="sxs-lookup"><span data-stu-id="603ff-130">Requirements</span></span>  
 <span data-ttu-id="603ff-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="603ff-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="603ff-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="603ff-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="603ff-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="603ff-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="603ff-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="603ff-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603ff-135">См. также</span><span class="sxs-lookup"><span data-stu-id="603ff-135">See also</span></span>

- [<span data-ttu-id="603ff-136">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="603ff-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="603ff-137">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="603ff-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
