---
title: "Метод IHostTaskManager::SetCLRTaskManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9f009fee3f9bc439ce61d859759870f9cbb54f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="24b5d-102">Метод IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="24b5d-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="24b5d-103">Предоставляет основному указатель интерфейса [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="24b5d-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24b5d-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24b5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24b5d-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="24b5d-106">[in] Указатель на `ICLRTaskManager` экземпляр реализован средой CLR.</span><span class="sxs-lookup"><span data-stu-id="24b5d-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24b5d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24b5d-107">Return Value</span></span>  
  
|<span data-ttu-id="24b5d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24b5d-108">HRESULT</span></span>|<span data-ttu-id="24b5d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="24b5d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24b5d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="24b5d-110">S_OK</span></span>|<span data-ttu-id="24b5d-111">`SetCLRTaskManager`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="24b5d-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="24b5d-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24b5d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24b5d-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="24b5d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24b5d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="24b5d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="24b5d-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="24b5d-115">The call timed out.</span></span>|  
|<span data-ttu-id="24b5d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="24b5d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="24b5d-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="24b5d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="24b5d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="24b5d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="24b5d-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="24b5d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="24b5d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24b5d-120">E_FAIL</span></span>|<span data-ttu-id="24b5d-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="24b5d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24b5d-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="24b5d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24b5d-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="24b5d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24b5d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="24b5d-124">Remarks</span></span>  
 <span data-ttu-id="24b5d-125">Среда выполнения вызывает метод `SetCLRTaskManager` предоставить указатель интерфейса на узле `ICLRTaskManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="24b5d-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24b5d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="24b5d-126">Requirements</span></span>  
 <span data-ttu-id="24b5d-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24b5d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24b5d-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24b5d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24b5d-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24b5d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24b5d-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24b5d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b5d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="24b5d-131">See Also</span></span>  
 [<span data-ttu-id="24b5d-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="24b5d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="24b5d-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="24b5d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="24b5d-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="24b5d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="24b5d-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="24b5d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
