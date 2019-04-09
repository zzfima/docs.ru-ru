---
title: Метод IHostTaskManager::EnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4ef2971d9835070e9db72a5e5d370ff35c8edfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106445"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="013a1-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="013a1-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="013a1-103">Уведомляет основное приложение, что вызов неуправляемого метода, такие как неуправляемого метода, возвращается управление выполнением к общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="013a1-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="013a1-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="013a1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="013a1-105">Return Value</span></span>  
  
|<span data-ttu-id="013a1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="013a1-106">HRESULT</span></span>|<span data-ttu-id="013a1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="013a1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="013a1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="013a1-108">S_OK</span></span>|`EnterRuntime` <span data-ttu-id="013a1-109">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="013a1-109">returned successfully.</span></span>|  
|<span data-ttu-id="013a1-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="013a1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="013a1-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="013a1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="013a1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="013a1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="013a1-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="013a1-113">The call timed out.</span></span>|  
|<span data-ttu-id="013a1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="013a1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="013a1-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="013a1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="013a1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="013a1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="013a1-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="013a1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="013a1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="013a1-118">E_FAIL</span></span>|<span data-ttu-id="013a1-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="013a1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="013a1-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="013a1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="013a1-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="013a1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="013a1-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="013a1-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="013a1-123">Не хватает памяти была доступна для выполнения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="013a1-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="013a1-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="013a1-124">Remarks</span></span>  
 `EnterRuntime` <span data-ttu-id="013a1-125">вызывается для уведомления узла, неуправляемой функции, для которого предыдущими вызовами [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) метода был сделан, завершения выполнения и возвращает управление выполнением в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="013a1-125">is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="013a1-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла, неуправляемой функции, для которого предыдущими вызовами `LeaveRuntime` был сделан, осуществляет вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="013a1-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="013a1-127">Требования</span><span class="sxs-lookup"><span data-stu-id="013a1-127">Requirements</span></span>  
 <span data-ttu-id="013a1-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="013a1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="013a1-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="013a1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="013a1-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="013a1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="013a1-131">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="013a1-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="013a1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="013a1-132">See also</span></span>

- [<span data-ttu-id="013a1-133">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="013a1-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="013a1-134">Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода, с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="013a1-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="013a1-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="013a1-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="013a1-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="013a1-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="013a1-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="013a1-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="013a1-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="013a1-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="013a1-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="013a1-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
