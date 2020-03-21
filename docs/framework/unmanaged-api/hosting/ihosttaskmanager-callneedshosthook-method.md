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
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176296"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="93078-102">Метод IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="93078-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="93078-103">Позволяет хосту указать, может ли время выполнения общего языка (CLR) ввести указанный вызов в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="93078-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93078-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93078-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93078-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93078-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="93078-106">(в) Адрес в отображенный портативный исполняемый (PE) файл неуправляемой функции, которая должна быть вызвана.</span><span class="sxs-lookup"><span data-stu-id="93078-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="93078-107">(ваут) Указатель на значение Boolean, которое указывает, требует ли хост крючковатого вызова.</span><span class="sxs-lookup"><span data-stu-id="93078-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93078-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="93078-108">Return Value</span></span>  
  
|<span data-ttu-id="93078-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93078-109">HRESULT</span></span>|<span data-ttu-id="93078-110">Описание</span><span class="sxs-lookup"><span data-stu-id="93078-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93078-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="93078-111">S_OK</span></span>|<span data-ttu-id="93078-112">`CallNeedsHostHook`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="93078-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="93078-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="93078-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="93078-114">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="93078-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="93078-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="93078-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="93078-116">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="93078-116">The call timed out.</span></span>|  
|<span data-ttu-id="93078-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="93078-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="93078-118">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="93078-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="93078-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="93078-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="93078-120">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="93078-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="93078-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93078-121">E_FAIL</span></span>|<span data-ttu-id="93078-122">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="93078-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="93078-123">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="93078-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="93078-124">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="93078-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93078-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="93078-125">Remarks</span></span>  
 <span data-ttu-id="93078-126">Чтобы оптимизировать выполнение кода, CLR выполняет анализ каждой платформы вызова вызова во время компиляции, чтобы определить, можно ли выполнить вызов.</span><span class="sxs-lookup"><span data-stu-id="93078-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="93078-127">`CallNeedsHostHook`позволяет хосту переопределить это решение, требуя, чтобы вызов неуправляемой функции был подключен.</span><span class="sxs-lookup"><span data-stu-id="93078-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="93078-128">Если хост требует сяткр, время выполнения не встраиваемый вызов.</span><span class="sxs-lookup"><span data-stu-id="93078-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="93078-129">Как правило, хосту потребуется крючок, в котором он должен настроить состояние плавающей точки, или при получении уведомления о том, что вызов входит в состояние, в котором хост не может отслеживать запросы на память во время выполнения или любые блокировки.</span><span class="sxs-lookup"><span data-stu-id="93078-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="93078-130">Когда хост требует, чтобы вызов был подключен, время выполнения уведомляет множество переходов к управляемому коду и из его, используя вызовы [enterRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) [LeaveRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)и [ReverseLeaveRuntime.](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)</span><span class="sxs-lookup"><span data-stu-id="93078-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93078-131">Требования</span><span class="sxs-lookup"><span data-stu-id="93078-131">Requirements</span></span>  
 <span data-ttu-id="93078-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93078-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93078-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93078-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93078-134">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93078-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93078-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93078-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93078-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93078-136">See also</span></span>

- [<span data-ttu-id="93078-137">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="93078-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="93078-138">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="93078-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="93078-139">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="93078-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="93078-140">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="93078-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
