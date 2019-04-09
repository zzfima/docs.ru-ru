---
title: Метод IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adc270be51988cba78c6e522b16b480baef725c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139234"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="bfab9-102">Метод IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="bfab9-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="bfab9-103">Ведущее приложение может указать, сможет ли среда CLR (CLR) вводить заданный вызов в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="bfab9-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfab9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfab9-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfab9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfab9-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="bfab9-106">[in] Адрес в файле сопоставленные переносимого исполняемого (PE) из неуправляемой функции, который должен вызываться.</span><span class="sxs-lookup"><span data-stu-id="bfab9-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="bfab9-107">[out] Указатель на логическое значение, указывающее, требуется ли узел вызова связать.</span><span class="sxs-lookup"><span data-stu-id="bfab9-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfab9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfab9-108">Return Value</span></span>  
  
|<span data-ttu-id="bfab9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfab9-109">HRESULT</span></span>|<span data-ttu-id="bfab9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bfab9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfab9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfab9-111">S_OK</span></span>|`CallNeedsHostHook` <span data-ttu-id="bfab9-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="bfab9-112">returned successfully.</span></span>|  
|<span data-ttu-id="bfab9-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfab9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfab9-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bfab9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfab9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfab9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfab9-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="bfab9-116">The call timed out.</span></span>|  
|<span data-ttu-id="bfab9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfab9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfab9-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="bfab9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfab9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfab9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfab9-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="bfab9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfab9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfab9-121">E_FAIL</span></span>|<span data-ttu-id="bfab9-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="bfab9-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="bfab9-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bfab9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfab9-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bfab9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfab9-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="bfab9-125">Remarks</span></span>  
 <span data-ttu-id="bfab9-126">Чтобы оптимизировать выполнение кода, среда CLR выполняет анализ каждого вызова неуправляемого кода во время компиляции, чтобы определить, можно ли вызов как встроенный.</span><span class="sxs-lookup"><span data-stu-id="bfab9-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> `CallNeedsHostHook` <span data-ttu-id="bfab9-127">Позволяет ведущему приложению переопределить это решение, требуя связать вызова неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="bfab9-127">enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="bfab9-128">Если узлу требуется обработчик, среда выполнения не вводит вызов.</span><span class="sxs-lookup"><span data-stu-id="bfab9-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="bfab9-129">Узел обычно требуется в случае необходимости настройки состояния с плавающей запятой, или при получении уведомления, что вызов переходит в состояние, где узел не может отслеживать запросы среды выполнения памяти или любое число блокировок.</span><span class="sxs-lookup"><span data-stu-id="bfab9-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="bfab9-130">Если узел требуется связать вызов, среда выполнения уведомляет основное приложение переходов в и из управляемого кода с помощью вызова [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), и [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="bfab9-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfab9-131">Требования</span><span class="sxs-lookup"><span data-stu-id="bfab9-131">Requirements</span></span>  
 <span data-ttu-id="bfab9-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfab9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfab9-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bfab9-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfab9-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfab9-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bfab9-135">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bfab9-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bfab9-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bfab9-136">See also</span></span>

- [<span data-ttu-id="bfab9-137">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="bfab9-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="bfab9-138">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="bfab9-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="bfab9-139">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="bfab9-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="bfab9-140">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="bfab9-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
