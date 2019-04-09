---
title: Метод IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 283e390b024fd1d0d6a51659b67eff82477fc64d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173554"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="a04eb-102">Метод IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a04eb-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="a04eb-103">Предоставляет указатель интерфейса на узле [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) экземпляра, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="a04eb-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a04eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a04eb-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a04eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a04eb-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="a04eb-106">[in] Указатель на `ICLRTaskManager` экземпляра, реализуемый среда CLR.</span><span class="sxs-lookup"><span data-stu-id="a04eb-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a04eb-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a04eb-107">Return Value</span></span>  
  
|<span data-ttu-id="a04eb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a04eb-108">HRESULT</span></span>|<span data-ttu-id="a04eb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a04eb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a04eb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a04eb-110">S_OK</span></span>|`SetCLRTaskManager` <span data-ttu-id="a04eb-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a04eb-111">returned successfully.</span></span>|  
|<span data-ttu-id="a04eb-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a04eb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a04eb-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a04eb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a04eb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a04eb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a04eb-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a04eb-115">The call timed out.</span></span>|  
|<span data-ttu-id="a04eb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a04eb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a04eb-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a04eb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a04eb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a04eb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a04eb-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a04eb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a04eb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a04eb-120">E_FAIL</span></span>|<span data-ttu-id="a04eb-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a04eb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a04eb-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a04eb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a04eb-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a04eb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a04eb-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="a04eb-124">Remarks</span></span>  
 <span data-ttu-id="a04eb-125">Среда выполнения вызывает `SetCLRTaskManager` предоставить указатель интерфейса на узле `ICLRTaskManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a04eb-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a04eb-126">Требования</span><span class="sxs-lookup"><span data-stu-id="a04eb-126">Requirements</span></span>  
 <span data-ttu-id="a04eb-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a04eb-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a04eb-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a04eb-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a04eb-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a04eb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a04eb-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a04eb-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a04eb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a04eb-131">See also</span></span>

- [<span data-ttu-id="a04eb-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a04eb-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a04eb-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a04eb-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a04eb-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="a04eb-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a04eb-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a04eb-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
