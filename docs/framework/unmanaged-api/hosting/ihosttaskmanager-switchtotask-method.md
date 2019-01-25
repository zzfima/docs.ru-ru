---
title: Метод IHostTaskManager::SwitchToTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c7bf550985b5177348541aaa148c88c7c205258
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490721"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="cb444-102">Метод IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="cb444-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="cb444-103">Уведомляет основное приложение, что он должен исходящего переключения текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="cb444-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb444-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb444-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb444-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb444-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="cb444-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений перечисления, указывающий действие, выполняемое узлом, если в блоках запрошенную операцию.</span><span class="sxs-lookup"><span data-stu-id="cb444-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb444-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb444-107">Return Value</span></span>  
  
|<span data-ttu-id="cb444-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb444-108">HRESULT</span></span>|<span data-ttu-id="cb444-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cb444-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb444-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb444-110">S_OK</span></span>|<span data-ttu-id="cb444-111">`SwitchToTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cb444-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="cb444-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb444-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb444-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cb444-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb444-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb444-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb444-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cb444-115">The call timed out.</span></span>|  
|<span data-ttu-id="cb444-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb444-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb444-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cb444-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb444-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb444-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb444-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cb444-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb444-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb444-120">E_FAIL</span></span>|<span data-ttu-id="cb444-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="cb444-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb444-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cb444-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb444-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb444-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb444-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb444-124">Remarks</span></span>  
 <span data-ttu-id="cb444-125">Узел можно переключиться в другой задаче предпочтительную или необходимую.</span><span class="sxs-lookup"><span data-stu-id="cb444-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb444-126">`SwitchToTask` Задает задачу, узел следует переключиться в режим; он указывает только задание, которое необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="cb444-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb444-127">Требования</span><span class="sxs-lookup"><span data-stu-id="cb444-127">Requirements</span></span>  
 <span data-ttu-id="cb444-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb444-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb444-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb444-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb444-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb444-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb444-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb444-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb444-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cb444-132">See also</span></span>
- [<span data-ttu-id="cb444-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="cb444-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cb444-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="cb444-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cb444-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="cb444-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cb444-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cb444-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
