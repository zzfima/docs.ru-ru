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
ms.openlocfilehash: 9074201cb56ad9e6c4ddadc8468d2ceadbafcb75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749311"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="51e80-102">Метод IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="51e80-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="51e80-103">Уведомляет основное приложение, что он должен исходящего переключения текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="51e80-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51e80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51e80-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51e80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51e80-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="51e80-106">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений перечисления, указывающий действие, выполняемое узлом, если в блоках запрошенную операцию.</span><span class="sxs-lookup"><span data-stu-id="51e80-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51e80-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51e80-107">Return Value</span></span>  
  
|<span data-ttu-id="51e80-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51e80-108">HRESULT</span></span>|<span data-ttu-id="51e80-109">Описание</span><span class="sxs-lookup"><span data-stu-id="51e80-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51e80-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="51e80-110">S_OK</span></span>|<span data-ttu-id="51e80-111">`SwitchToTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="51e80-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="51e80-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51e80-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51e80-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="51e80-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51e80-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51e80-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51e80-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="51e80-115">The call timed out.</span></span>|  
|<span data-ttu-id="51e80-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51e80-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51e80-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="51e80-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51e80-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51e80-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51e80-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="51e80-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51e80-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51e80-120">E_FAIL</span></span>|<span data-ttu-id="51e80-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="51e80-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51e80-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="51e80-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51e80-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51e80-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51e80-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="51e80-124">Remarks</span></span>  
 <span data-ttu-id="51e80-125">Узел можно переключиться в другой задаче предпочтительную или необходимую.</span><span class="sxs-lookup"><span data-stu-id="51e80-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e80-126">`SwitchToTask` Задает задачу, узел следует переключиться в режим; он указывает только задание, которое необходимо отключить.</span><span class="sxs-lookup"><span data-stu-id="51e80-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e80-127">Требования</span><span class="sxs-lookup"><span data-stu-id="51e80-127">Requirements</span></span>  
 <span data-ttu-id="51e80-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51e80-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e80-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51e80-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51e80-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51e80-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51e80-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e80-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e80-132">См. также</span><span class="sxs-lookup"><span data-stu-id="51e80-132">See also</span></span>

- [<span data-ttu-id="51e80-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="51e80-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="51e80-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="51e80-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="51e80-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="51e80-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="51e80-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="51e80-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
