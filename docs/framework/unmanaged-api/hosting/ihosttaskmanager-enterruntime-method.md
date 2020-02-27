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
ms.openlocfilehash: 94ad0073678e88e15d4b083793dca1423130f7e9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628090"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="474d2-102">Метод IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="474d2-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="474d2-103">Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением среде CLR.</span><span class="sxs-lookup"><span data-stu-id="474d2-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="474d2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="474d2-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="474d2-105">Return Value</span></span>  
  
|<span data-ttu-id="474d2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="474d2-106">HRESULT</span></span>|<span data-ttu-id="474d2-107">Description</span><span class="sxs-lookup"><span data-stu-id="474d2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="474d2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="474d2-108">S_OK</span></span>|<span data-ttu-id="474d2-109">`EnterRuntime` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="474d2-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="474d2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="474d2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="474d2-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="474d2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="474d2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="474d2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="474d2-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="474d2-113">The call timed out.</span></span>|  
|<span data-ttu-id="474d2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="474d2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="474d2-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="474d2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="474d2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="474d2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="474d2-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="474d2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="474d2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="474d2-118">E_FAIL</span></span>|<span data-ttu-id="474d2-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="474d2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="474d2-120">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="474d2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="474d2-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="474d2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="474d2-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="474d2-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="474d2-123">Недостаточно памяти для завершения запрошенного выделения.</span><span class="sxs-lookup"><span data-stu-id="474d2-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="474d2-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="474d2-124">Remarks</span></span>  
 <span data-ttu-id="474d2-125">`EnterRuntime` вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов метода [леаверунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) , завершила выполнение, и возвращает управление выполнением среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="474d2-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="474d2-126">[Реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов `LeaveRuntime`, делает вызов управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="474d2-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="474d2-127">Требования</span><span class="sxs-lookup"><span data-stu-id="474d2-127">Requirements</span></span>  
 <span data-ttu-id="474d2-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="474d2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="474d2-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="474d2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="474d2-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="474d2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="474d2-131">**.NET Framework версии:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="474d2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474d2-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="474d2-132">See also</span></span>

- <span data-ttu-id="474d2-133">[Расширенное COM-взаимодействие](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="474d2-133">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="474d2-134">Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke</span><span class="sxs-lookup"><span data-stu-id="474d2-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="474d2-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="474d2-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="474d2-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="474d2-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="474d2-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="474d2-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="474d2-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="474d2-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="474d2-139">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="474d2-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
