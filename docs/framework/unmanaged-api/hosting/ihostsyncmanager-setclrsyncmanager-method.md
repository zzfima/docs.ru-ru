---
title: Метод IHostSyncManager::SetCLRSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aef7866d912951972ec9c66efccca671c3787da6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="de485-102">Метод IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="de485-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="de485-103">Наборы [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) экземпляра для связи с текущим [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="de485-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de485-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de485-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de485-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de485-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="de485-106">[in] Указатель на `ICLRSyncManager` экземпляра, предоставляемые общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="de485-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de485-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="de485-107">Return Value</span></span>  
  
|<span data-ttu-id="de485-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de485-108">HRESULT</span></span>|<span data-ttu-id="de485-109">Описание</span><span class="sxs-lookup"><span data-stu-id="de485-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de485-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="de485-110">S_OK</span></span>|<span data-ttu-id="de485-111">`SetCLRSyncManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="de485-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="de485-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="de485-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="de485-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="de485-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="de485-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="de485-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="de485-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="de485-115">The call timed out.</span></span>|  
|<span data-ttu-id="de485-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="de485-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="de485-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="de485-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="de485-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="de485-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="de485-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="de485-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="de485-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="de485-120">E_FAIL</span></span>|<span data-ttu-id="de485-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="de485-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="de485-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="de485-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="de485-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="de485-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de485-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="de485-124">Remarks</span></span>  
 <span data-ttu-id="de485-125">Для упрощения взаимодействия между узлом и среда CLR, интерфейсы размещения обычно представлены парами.</span><span class="sxs-lookup"><span data-stu-id="de485-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="de485-126">Один член пары, реализуемых основным приложением и средой CLR реализуется другого элемента.</span><span class="sxs-lookup"><span data-stu-id="de485-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="de485-127">Как реализация главного узла `IHostSyncManager` соответствующий интерфейс `ICLRSyncManager` интерфейс, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="de485-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="de485-128">Среда CLR вызывает `SetCLRSyncManager` для предоставления `ICLRSyncManager` экземпляра для связывания с текущего узла `IHostSyncManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="de485-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de485-129">Требования</span><span class="sxs-lookup"><span data-stu-id="de485-129">Requirements</span></span>  
 <span data-ttu-id="de485-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de485-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de485-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de485-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de485-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de485-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de485-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de485-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de485-134">См. также</span><span class="sxs-lookup"><span data-stu-id="de485-134">See Also</span></span>  
 [<span data-ttu-id="de485-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="de485-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="de485-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="de485-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
