---
title: "Метод IHostTaskManager::ReverseEnterRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseEnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69743f6b7229f89d19d4134a11bb5f37fe5ca928
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="d42c7-102">Метод IHostTaskManager::ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="d42c7-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="d42c7-103">Уведомляет узел, что вызов в среде (CLR) из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d42c7-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d42c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d42c7-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d42c7-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d42c7-105">Return Value</span></span>  
  
|<span data-ttu-id="d42c7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d42c7-106">HRESULT</span></span>|<span data-ttu-id="d42c7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d42c7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d42c7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d42c7-108">S_OK</span></span>|<span data-ttu-id="d42c7-109">`ReverseEnterRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d42c7-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="d42c7-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d42c7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d42c7-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d42c7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d42c7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d42c7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d42c7-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d42c7-113">The call timed out.</span></span>|  
|<span data-ttu-id="d42c7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d42c7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d42c7-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d42c7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d42c7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d42c7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d42c7-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d42c7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d42c7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d42c7-118">E_FAIL</span></span>|<span data-ttu-id="d42c7-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d42c7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d42c7-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d42c7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d42c7-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d42c7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d42c7-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d42c7-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d42c7-123">Недостаточно памяти для выполнения запрашиваемого выделения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d42c7-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d42c7-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d42c7-124">Remarks</span></span>  
 <span data-ttu-id="d42c7-125">Если в среде CLR вызов из последовательность, которая была создана в управляемом коде, при каждом вызове функции `ReverseEnterRuntime` соответствует вызов [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="d42c7-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d42c7-126">Вызовы могут осуществляться из неуправляемого кода без вложения.</span><span class="sxs-lookup"><span data-stu-id="d42c7-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="d42c7-127">В этом случае отсутствует вызов к [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), или `ReverseLeaveRuntime`и число вызовов `ReverseEnterRuntime` не равно числу вызовов `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="d42c7-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d42c7-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d42c7-128">Requirements</span></span>  
 <span data-ttu-id="d42c7-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d42c7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d42c7-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d42c7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d42c7-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d42c7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d42c7-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d42c7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d42c7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d42c7-133">See Also</span></span>  
 [<span data-ttu-id="d42c7-134">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d42c7-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d42c7-135">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d42c7-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d42c7-136">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="d42c7-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d42c7-137">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d42c7-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
