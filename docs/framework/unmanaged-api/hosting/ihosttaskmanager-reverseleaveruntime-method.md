---
title: "Метод IHostTaskManager::ReverseLeaveRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseLeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 634465e2d78dbac41b8791d5be44b2821744f07d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="4a3c5-102">Метод IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="4a3c5-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="4a3c5-103">Уведомляет основное приложение, что элемент управления оставляя общеязыковой среды выполнения (CLR) и неуправляемой функции, которая, в свою очередь, была вызвана из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a3c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a3c5-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4a3c5-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a3c5-105">Return Value</span></span>  
  
|<span data-ttu-id="4a3c5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a3c5-106">HRESULT</span></span>|<span data-ttu-id="4a3c5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4a3c5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a3c5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a3c5-108">S_OK</span></span>|<span data-ttu-id="4a3c5-109">`ReverseLeaveRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="4a3c5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a3c5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a3c5-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a3c5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a3c5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a3c5-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-113">The call timed out.</span></span>|  
|<span data-ttu-id="4a3c5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a3c5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a3c5-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a3c5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a3c5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a3c5-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a3c5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a3c5-118">E_FAIL</span></span>|<span data-ttu-id="4a3c5-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a3c5-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a3c5-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a3c5-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a3c5-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4a3c5-123">Недостаточно памяти для выполнения запрашиваемого выделения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a3c5-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a3c5-124">Remarks</span></span>  
 <span data-ttu-id="4a3c5-125">Среда CLR вызывает `ReverseLeaveRuntime` для оповещения о том, что текущая выполняющаяся задача возвращает узел элемента управления в неуправляемую функцию, которая в свою очередь, была вызвана из управляемого кода посредством вызова.</span><span class="sxs-lookup"><span data-stu-id="4a3c5-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="4a3c5-126">Каждый вызов `ReverseLeaveRuntime` совпадает с соответствующим вызовом [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="4a3c5-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a3c5-127">Требования</span><span class="sxs-lookup"><span data-stu-id="4a3c5-127">Requirements</span></span>  
 <span data-ttu-id="4a3c5-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a3c5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a3c5-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a3c5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a3c5-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a3c5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a3c5-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a3c5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3c5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4a3c5-132">See Also</span></span>  
 [<span data-ttu-id="4a3c5-133">Метод CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="4a3c5-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)  
 [<span data-ttu-id="4a3c5-134">Метод EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="4a3c5-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)  
 [<span data-ttu-id="4a3c5-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4a3c5-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4a3c5-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4a3c5-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4a3c5-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4a3c5-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="4a3c5-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4a3c5-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4a3c5-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="4a3c5-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)  
 [<span data-ttu-id="4a3c5-140">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="4a3c5-140">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)
