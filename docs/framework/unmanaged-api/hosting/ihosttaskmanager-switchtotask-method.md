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
ms.openlocfilehash: a55b43f3629cebb0ba1d3a7ac1802126874418d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122118"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="cb88f-102">Метод IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="cb88f-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="cb88f-103">Уведомляет узел о том, что необходимо отключить текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="cb88f-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb88f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb88f-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb88f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb88f-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="cb88f-106">окне Одно из значений перечисления [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , указывающее действие, которое должен выполнить узел, если запрошенная операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="cb88f-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb88f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb88f-107">Return Value</span></span>  
  
|<span data-ttu-id="cb88f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb88f-108">HRESULT</span></span>|<span data-ttu-id="cb88f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cb88f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb88f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb88f-110">S_OK</span></span>|<span data-ttu-id="cb88f-111">`SwitchToTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="cb88f-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="cb88f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb88f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb88f-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cb88f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb88f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb88f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb88f-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="cb88f-115">The call timed out.</span></span>|  
|<span data-ttu-id="cb88f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb88f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb88f-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="cb88f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb88f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb88f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb88f-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="cb88f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb88f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb88f-120">E_FAIL</span></span>|<span data-ttu-id="cb88f-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="cb88f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb88f-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cb88f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb88f-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb88f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb88f-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="cb88f-124">Remarks</span></span>  
 <span data-ttu-id="cb88f-125">Узел может переключиться на другую задачу по мере необходимости или необходимости.</span><span class="sxs-lookup"><span data-stu-id="cb88f-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb88f-126">`SwitchToTask` не указывает, в какую задачу должен переключаться узел; Он указывает только задачу, с которой она должна переключаться.</span><span class="sxs-lookup"><span data-stu-id="cb88f-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb88f-127">Требования</span><span class="sxs-lookup"><span data-stu-id="cb88f-127">Requirements</span></span>  
 <span data-ttu-id="cb88f-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb88f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb88f-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb88f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb88f-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cb88f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb88f-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb88f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb88f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cb88f-132">See also</span></span>

- [<span data-ttu-id="cb88f-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="cb88f-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cb88f-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="cb88f-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cb88f-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="cb88f-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cb88f-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cb88f-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
