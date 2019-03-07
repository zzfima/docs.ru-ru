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
ms.openlocfilehash: b27cf1ab377a3bb51700b287024d801e75107c8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464925"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="969ee-102">Метод IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="969ee-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="969ee-103">Наборы [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) экземпляра, связываемый с текущим [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="969ee-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="969ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="969ee-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="969ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="969ee-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="969ee-106">[in] Указатель на `ICLRSyncManager` экземпляра, предоставляемые общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="969ee-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="969ee-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="969ee-107">Return Value</span></span>  
  
|<span data-ttu-id="969ee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="969ee-108">HRESULT</span></span>|<span data-ttu-id="969ee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="969ee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="969ee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="969ee-110">S_OK</span></span>|<span data-ttu-id="969ee-111">`SetCLRSyncManager` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="969ee-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="969ee-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="969ee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="969ee-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="969ee-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="969ee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="969ee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="969ee-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="969ee-115">The call timed out.</span></span>|  
|<span data-ttu-id="969ee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="969ee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="969ee-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="969ee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="969ee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="969ee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="969ee-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="969ee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="969ee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="969ee-120">E_FAIL</span></span>|<span data-ttu-id="969ee-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="969ee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="969ee-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="969ee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="969ee-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="969ee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="969ee-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="969ee-124">Remarks</span></span>  
 <span data-ttu-id="969ee-125">Для упрощения взаимодействия между узлом и среда CLR, интерфейсы размещения обычно представлены парами.</span><span class="sxs-lookup"><span data-stu-id="969ee-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="969ee-126">Один член пары, реализуемого ведущим, и другой член реализуется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="969ee-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="969ee-127">Как ведущий реализацию `IHostSyncManager` соответствующий интерфейс `ICLRSyncManager` интерфейс, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="969ee-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="969ee-128">Среда CLR вызывает `SetCLRSyncManager` для предоставления `ICLRSyncManager` экземпляра для узла, связываемый с текущим `IHostSyncManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="969ee-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="969ee-129">Требования</span><span class="sxs-lookup"><span data-stu-id="969ee-129">Requirements</span></span>  
 <span data-ttu-id="969ee-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="969ee-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="969ee-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="969ee-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="969ee-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="969ee-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="969ee-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="969ee-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="969ee-134">См. также</span><span class="sxs-lookup"><span data-stu-id="969ee-134">See also</span></span>
- [<span data-ttu-id="969ee-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="969ee-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="969ee-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="969ee-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
