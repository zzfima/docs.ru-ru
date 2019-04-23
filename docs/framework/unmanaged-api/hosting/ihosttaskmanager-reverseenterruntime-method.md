---
title: Метод IHostTaskManager::ReverseEnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6eefdaf5dee423b0a9ae054446224a3ea97e3c9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213783"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="dae32-102">Метод IHostTaskManager::ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="dae32-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="dae32-103">Уведомляет основное приложение, что вызов в среду (CLR) из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="dae32-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dae32-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dae32-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dae32-105">Return Value</span></span>  
  
|<span data-ttu-id="dae32-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dae32-106">HRESULT</span></span>|<span data-ttu-id="dae32-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dae32-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dae32-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dae32-108">S_OK</span></span>|<span data-ttu-id="dae32-109">`ReverseEnterRuntime` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dae32-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="dae32-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dae32-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dae32-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dae32-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dae32-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dae32-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dae32-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dae32-113">The call timed out.</span></span>|  
|<span data-ttu-id="dae32-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dae32-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dae32-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dae32-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dae32-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dae32-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dae32-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dae32-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dae32-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dae32-118">E_FAIL</span></span>|<span data-ttu-id="dae32-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="dae32-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dae32-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dae32-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dae32-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dae32-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dae32-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dae32-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dae32-123">Недостаточно памяти для завершения выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="dae32-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dae32-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="dae32-124">Remarks</span></span>  
 <span data-ttu-id="dae32-125">Если в среде CLR вызов из последовательность, которая была создана в управляемом коде, при каждом вызове `ReverseEnterRuntime` соответствующий вызов [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="dae32-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dae32-126">Звонки могут происходить из неуправляемого кода без вложения.</span><span class="sxs-lookup"><span data-stu-id="dae32-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="dae32-127">В этом случае отсутствует вызов к [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), или `ReverseLeaveRuntime`и число вызовов `ReverseEnterRuntime` равно числу вызовов `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="dae32-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae32-128">Требования</span><span class="sxs-lookup"><span data-stu-id="dae32-128">Requirements</span></span>  
 <span data-ttu-id="dae32-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae32-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae32-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dae32-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dae32-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dae32-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dae32-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae32-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae32-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dae32-133">See also</span></span>

- [<span data-ttu-id="dae32-134">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dae32-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dae32-135">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dae32-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dae32-136">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="dae32-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dae32-137">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dae32-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
