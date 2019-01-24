---
title: Метод ICLRTask::LocksHeld
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 931395a1bb5f516000097f964ce0372a69420d85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679634"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="27aa3-102">Метод ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="27aa3-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="27aa3-103">Возвращает число блокировок, произведенных в задаче.</span><span class="sxs-lookup"><span data-stu-id="27aa3-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27aa3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27aa3-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27aa3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27aa3-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="27aa3-106">[out] Число блокировок, удерживаемых в задаче во время вызова метода.</span><span class="sxs-lookup"><span data-stu-id="27aa3-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27aa3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27aa3-107">Return Value</span></span>  
  
|<span data-ttu-id="27aa3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27aa3-108">HRESULT</span></span>|<span data-ttu-id="27aa3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="27aa3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27aa3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="27aa3-110">S_OK</span></span>|<span data-ttu-id="27aa3-111">`LocksHeld` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="27aa3-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="27aa3-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27aa3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27aa3-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="27aa3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27aa3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27aa3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27aa3-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="27aa3-115">The call timed out.</span></span>|  
|<span data-ttu-id="27aa3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27aa3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27aa3-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="27aa3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27aa3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27aa3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27aa3-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="27aa3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27aa3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27aa3-120">E_FAIL</span></span>|<span data-ttu-id="27aa3-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="27aa3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27aa3-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="27aa3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27aa3-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27aa3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27aa3-124">Требования</span><span class="sxs-lookup"><span data-stu-id="27aa3-124">Requirements</span></span>  
 <span data-ttu-id="27aa3-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27aa3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27aa3-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27aa3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27aa3-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27aa3-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27aa3-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27aa3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27aa3-129">См. также</span><span class="sxs-lookup"><span data-stu-id="27aa3-129">See also</span></span>
- [<span data-ttu-id="27aa3-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="27aa3-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="27aa3-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="27aa3-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="27aa3-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="27aa3-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="27aa3-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="27aa3-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
