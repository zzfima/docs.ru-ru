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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b5a389af718322d1e0fffebae046bf28731877b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435781"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="7834b-102">Метод ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="7834b-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="7834b-103">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="7834b-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7834b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7834b-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7834b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7834b-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="7834b-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывает, что операция среды выполнения (CLR) общий язык, для которого требуется задать время ожидания.</span><span class="sxs-lookup"><span data-stu-id="7834b-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="7834b-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7834b-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="7834b-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="7834b-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="7834b-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="7834b-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="7834b-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7834b-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="7834b-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7834b-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="7834b-112">[in] Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="7834b-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="7834b-113">Значение INFINITE вызывает операции никогда не времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="7834b-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7834b-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7834b-114">Return Value</span></span>  
  
|<span data-ttu-id="7834b-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7834b-115">HRESULT</span></span>|<span data-ttu-id="7834b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7834b-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7834b-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="7834b-117">S_OK</span></span>|<span data-ttu-id="7834b-118">`SetTimeout` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7834b-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="7834b-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7834b-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7834b-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7834b-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7834b-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7834b-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7834b-122">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7834b-122">The call timed out.</span></span>|  
|<span data-ttu-id="7834b-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7834b-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7834b-124">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7834b-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7834b-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7834b-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7834b-126">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7834b-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7834b-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7834b-127">E_FAIL</span></span>|<span data-ttu-id="7834b-128">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7834b-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7834b-129">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7834b-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7834b-130">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7834b-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7834b-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7834b-131">E_INVALIDARG</span></span>|<span data-ttu-id="7834b-132">Невозможно задать время ожидания для указанного `operation`, или было задано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="7834b-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7834b-133">Требования</span><span class="sxs-lookup"><span data-stu-id="7834b-133">Requirements</span></span>  
 <span data-ttu-id="7834b-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7834b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7834b-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7834b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7834b-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7834b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7834b-137">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7834b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7834b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7834b-138">See Also</span></span>  
 [<span data-ttu-id="7834b-139">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="7834b-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="7834b-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7834b-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="7834b-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7834b-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
