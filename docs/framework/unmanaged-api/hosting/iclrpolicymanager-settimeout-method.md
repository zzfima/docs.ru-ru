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
ms.openlocfilehash: 8edb16de4c02d2589ecfb9ae5becba22e10e6be6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609334"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="d134c-102">Метод ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="d134c-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="d134c-103">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="d134c-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d134c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d134c-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d134c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d134c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d134c-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающее, распространенные операции среды выполнения (CLR) языка, для которого требуется задать время ожидания.</span><span class="sxs-lookup"><span data-stu-id="d134c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="d134c-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d134c-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="d134c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d134c-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="d134c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d134c-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="d134c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d134c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="d134c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d134c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="d134c-112">[in] Новое значение времени ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="d134c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="d134c-113">Задано значение INFINITE приводит никогда не к времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="d134c-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d134c-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d134c-114">Return Value</span></span>  
  
|<span data-ttu-id="d134c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d134c-115">HRESULT</span></span>|<span data-ttu-id="d134c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d134c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d134c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d134c-117">S_OK</span></span>|<span data-ttu-id="d134c-118">`SetTimeout` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d134c-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="d134c-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d134c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d134c-120">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d134c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d134c-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d134c-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d134c-122">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d134c-122">The call timed out.</span></span>|  
|<span data-ttu-id="d134c-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d134c-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d134c-124">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d134c-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d134c-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d134c-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d134c-126">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d134c-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d134c-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d134c-127">E_FAIL</span></span>|<span data-ttu-id="d134c-128">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d134c-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d134c-129">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="d134c-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d134c-130">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d134c-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d134c-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d134c-131">E_INVALIDARG</span></span>|<span data-ttu-id="d134c-132">Невозможно задать время ожидания для указанного `operation`, или задано недопустимое значение `operation`.</span><span class="sxs-lookup"><span data-stu-id="d134c-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d134c-133">Требования</span><span class="sxs-lookup"><span data-stu-id="d134c-133">Requirements</span></span>  
 <span data-ttu-id="d134c-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d134c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d134c-135">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d134c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d134c-136">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d134c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d134c-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d134c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d134c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d134c-138">See also</span></span>
- [<span data-ttu-id="d134c-139">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="d134c-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="d134c-140">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d134c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d134c-141">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d134c-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
