---
title: "Метод IHostTaskManager::EnterRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70c9e83311fd7427895e1957d3511a45c47434e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="63309-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="63309-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="63309-103">Уведомляет основное приложение, вызов неуправляемого метода, такие как неуправляемого метода возвращает управление выполнением для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="63309-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63309-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63309-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="63309-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="63309-105">Return Value</span></span>  
  
|<span data-ttu-id="63309-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63309-106">HRESULT</span></span>|<span data-ttu-id="63309-107">Описание</span><span class="sxs-lookup"><span data-stu-id="63309-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63309-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="63309-108">S_OK</span></span>|<span data-ttu-id="63309-109">`EnterRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="63309-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="63309-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63309-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63309-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="63309-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63309-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63309-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63309-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="63309-113">The call timed out.</span></span>|  
|<span data-ttu-id="63309-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63309-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63309-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="63309-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63309-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63309-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63309-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="63309-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63309-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63309-118">E_FAIL</span></span>|<span data-ttu-id="63309-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="63309-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63309-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="63309-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63309-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63309-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="63309-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="63309-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="63309-123">Не хватает памяти была доступна для выполнения запрашиваемого распределения.</span><span class="sxs-lookup"><span data-stu-id="63309-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63309-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="63309-124">Remarks</span></span>  
 <span data-ttu-id="63309-125">`EnterRuntime`вызывается для уведомления узла, неуправляемые функции, для которого предыдущими вызовами метода [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) метод был сделан, закончила выполнение и возвращает управление выполнением в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="63309-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63309-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла, неуправляемые функции, для которого предыдущими вызовами метода `LeaveRuntime` был сделан, осуществляет вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="63309-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63309-127">Требования</span><span class="sxs-lookup"><span data-stu-id="63309-127">Requirements</span></span>  
 <span data-ttu-id="63309-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63309-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63309-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63309-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63309-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63309-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63309-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63309-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63309-132">См. также</span><span class="sxs-lookup"><span data-stu-id="63309-132">See Also</span></span>  
 [<span data-ttu-id="63309-133">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="63309-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="63309-134">Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="63309-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="63309-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="63309-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="63309-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="63309-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="63309-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="63309-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="63309-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="63309-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="63309-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="63309-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
