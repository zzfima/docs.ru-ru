---
title: "Метод IHostTaskManager::LeaveRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4c168cffba44a21d6705e8abd921ecbf8a9da6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="535b3-102">Метод IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="535b3-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="535b3-103">Уведомляет узел, что текущая выполняющаяся задача собирается оставьте общеязыковой среды выполнения (CLR) и введите неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="535b3-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="535b3-104">С соответствующим вызовом [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) уведомляет узел, что текущая выполняющаяся задача повторный ввод управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="535b3-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535b3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="535b3-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="535b3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="535b3-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="535b3-107">[in] Адрес в пределах сопоставленных переносимый исполняемый файл для вызова неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="535b3-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="535b3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="535b3-108">Return Value</span></span>  
  
|<span data-ttu-id="535b3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="535b3-109">HRESULT</span></span>|<span data-ttu-id="535b3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="535b3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="535b3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="535b3-111">S_OK</span></span>|<span data-ttu-id="535b3-112">`LeaveRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="535b3-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="535b3-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="535b3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="535b3-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="535b3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="535b3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="535b3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="535b3-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="535b3-116">The call timed out.</span></span>|  
|<span data-ttu-id="535b3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="535b3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="535b3-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="535b3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="535b3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="535b3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="535b3-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="535b3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="535b3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="535b3-121">E_FAIL</span></span>|<span data-ttu-id="535b3-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="535b3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="535b3-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="535b3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="535b3-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="535b3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="535b3-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="535b3-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="535b3-126">Недостаточно памяти для завершения запрошенной распределения.</span><span class="sxs-lookup"><span data-stu-id="535b3-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="535b3-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="535b3-127">Remarks</span></span>  
 <span data-ttu-id="535b3-128">Последовательность вызовов в и из неуправляемого кода могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="535b3-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="535b3-129">Например, в следующем списке представлены гипотетическую ситуацию, в котором последовательность вызовов `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), и `IHostTaskManager::EnterRuntime` предоставляет узлу возможность определить вложенные слои.</span><span class="sxs-lookup"><span data-stu-id="535b3-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="535b3-130">Действие</span><span class="sxs-lookup"><span data-stu-id="535b3-130">Action</span></span>|<span data-ttu-id="535b3-131">Вызов соответствующего метода</span><span class="sxs-lookup"><span data-stu-id="535b3-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="535b3-132">Вызвать неуправляемую функцию, написанную на языке C с помощью платформы управляемых исполняемая программа вызывает Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="535b3-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="535b3-133">Неуправляемые функции C вызывает метод в управляемой библиотеке DLL, написанные на C#.</span><span class="sxs-lookup"><span data-stu-id="535b3-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="535b3-134">Управляемые функции C# вызывает другую неуправляемую функцию, написанную на языке C, также вызове неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="535b3-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="535b3-135">Второй неуправляемая функция возвращает выполнение функции C#.</span><span class="sxs-lookup"><span data-stu-id="535b3-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="535b3-136">Функция C# возвращает результаты выполнения первой неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="535b3-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="535b3-137">Первая неуправляемая функция возвращает выполнение программы на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="535b3-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="535b3-138">Требования</span><span class="sxs-lookup"><span data-stu-id="535b3-138">Requirements</span></span>  
 <span data-ttu-id="535b3-139">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="535b3-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="535b3-140">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="535b3-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="535b3-141">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="535b3-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="535b3-142">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="535b3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535b3-143">См. также</span><span class="sxs-lookup"><span data-stu-id="535b3-143">See Also</span></span>  
 [<span data-ttu-id="535b3-144">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="535b3-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="535b3-145">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="535b3-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="535b3-146">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="535b3-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="535b3-147">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="535b3-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
