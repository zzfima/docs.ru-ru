---
title: Метод ICLRPolicyManager::SetTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 516ba1325404e757af8e38de239864b21b1640f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140759"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="1b5cd-102">Метод ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="1b5cd-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="1b5cd-103">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b5cd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b5cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b5cd-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="1b5cd-106">окне Одно из значений [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , указывающее на операцию среды CLR, для которой задается время ожидания.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="1b5cd-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1b5cd-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="1b5cd-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="1b5cd-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="1b5cd-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="1b5cd-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="1b5cd-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1b5cd-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="1b5cd-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1b5cd-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="1b5cd-112">окне Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="1b5cd-113">Значение INFINITE приводит к тому, что время ожидания операции никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b5cd-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1b5cd-114">Return Value</span></span>  
  
|<span data-ttu-id="1b5cd-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b5cd-115">HRESULT</span></span>|<span data-ttu-id="1b5cd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1b5cd-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b5cd-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b5cd-117">S_OK</span></span>|<span data-ttu-id="1b5cd-118">`SetTimeout` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="1b5cd-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b5cd-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b5cd-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b5cd-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b5cd-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b5cd-122">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-122">The call timed out.</span></span>|  
|<span data-ttu-id="1b5cd-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b5cd-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b5cd-124">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b5cd-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b5cd-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b5cd-126">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b5cd-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b5cd-127">E_FAIL</span></span>|<span data-ttu-id="1b5cd-128">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b5cd-129">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b5cd-130">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b5cd-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1b5cd-131">E_INVALIDARG</span></span>|<span data-ttu-id="1b5cd-132">Не удается задать время ожидания для указанного `operation`или указано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="1b5cd-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b5cd-133">Требования</span><span class="sxs-lookup"><span data-stu-id="1b5cd-133">Requirements</span></span>  
 <span data-ttu-id="1b5cd-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b5cd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b5cd-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1b5cd-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b5cd-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b5cd-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b5cd-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b5cd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5cd-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1b5cd-138">See also</span></span>

- [<span data-ttu-id="1b5cd-139">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="1b5cd-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="1b5cd-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1b5cd-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1b5cd-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="1b5cd-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
