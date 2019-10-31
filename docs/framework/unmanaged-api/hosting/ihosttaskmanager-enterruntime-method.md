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
ms.openlocfilehash: a3af57859c5284ff45681ffc2b5aa3ea3cf8fad6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133062"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="cd93a-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="cd93a-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="cd93a-103">Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением среде CLR.</span><span class="sxs-lookup"><span data-stu-id="cd93a-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd93a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd93a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cd93a-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cd93a-105">Return Value</span></span>  
  
|<span data-ttu-id="cd93a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd93a-106">HRESULT</span></span>|<span data-ttu-id="cd93a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cd93a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd93a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd93a-108">S_OK</span></span>|<span data-ttu-id="cd93a-109">`EnterRuntime` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="cd93a-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="cd93a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd93a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd93a-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cd93a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd93a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd93a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd93a-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="cd93a-113">The call timed out.</span></span>|  
|<span data-ttu-id="cd93a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd93a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd93a-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="cd93a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd93a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd93a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd93a-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="cd93a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd93a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd93a-118">E_FAIL</span></span>|<span data-ttu-id="cd93a-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="cd93a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd93a-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cd93a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd93a-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cd93a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd93a-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cd93a-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cd93a-123">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="cd93a-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd93a-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="cd93a-124">Remarks</span></span>  
 <span data-ttu-id="cd93a-125">`EnterRuntime` вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов метода [леаверунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) , завершила выполнение, и возвращает управление выполнением среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="cd93a-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd93a-126">[Реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов `LeaveRuntime`, делает вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="cd93a-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd93a-127">Требования</span><span class="sxs-lookup"><span data-stu-id="cd93a-127">Requirements</span></span>  
 <span data-ttu-id="cd93a-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd93a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd93a-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cd93a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd93a-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd93a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd93a-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd93a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd93a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cd93a-132">See also</span></span>

- [<span data-ttu-id="cd93a-133">Расширенное COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="cd93a-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="cd93a-134">Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="cd93a-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="cd93a-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="cd93a-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cd93a-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="cd93a-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cd93a-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="cd93a-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cd93a-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cd93a-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="cd93a-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="cd93a-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
