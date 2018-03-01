---
title: "Метод ICLRPolicyManager::SetActionOnTimeout"
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
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db0918272a315e78191624cbe6420863285620c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="d5526-102">Метод ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="d5526-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="d5526-103">Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), после истечения указанного времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="d5526-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5526-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5526-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5526-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5526-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d5526-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывает, что операция, для которого требуется задать время ожидания действия.</span><span class="sxs-lookup"><span data-stu-id="d5526-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="d5526-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d5526-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="d5526-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d5526-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="d5526-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d5526-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="d5526-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d5526-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="d5526-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d5526-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="d5526-112">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее политику действие, выполняемое после истечения времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="d5526-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5526-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5526-113">Return Value</span></span>  
  
|<span data-ttu-id="d5526-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5526-114">HRESULT</span></span>|<span data-ttu-id="d5526-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d5526-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5526-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5526-116">S_OK</span></span>|<span data-ttu-id="d5526-117">`SetActionOnTimeout`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d5526-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="d5526-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5526-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5526-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d5526-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5526-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5526-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5526-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d5526-121">The call timed out.</span></span>|  
|<span data-ttu-id="d5526-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5526-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5526-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d5526-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5526-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5526-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5526-125">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d5526-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5526-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5526-126">E_FAIL</span></span>|<span data-ttu-id="d5526-127">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d5526-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5526-128">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d5526-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5526-129">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d5526-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5526-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d5526-130">E_INVALIDARG</span></span>|<span data-ttu-id="d5526-131">Невозможно задать время ожидания для указанного `operation`, или было задано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="d5526-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5526-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5526-132">Remarks</span></span>  
 <span data-ttu-id="d5526-133">Значение времени ожидания может быть время ожидания по умолчанию, заданное в среде CLR или значения, указанного в узле в вызове [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d5526-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="d5526-134">Не все значения действий политики может быть указан как поведение времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d5526-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="d5526-135">`SetActionOnTimeout`обычно используется только для повышения поведение.</span><span class="sxs-lookup"><span data-stu-id="d5526-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="d5526-136">Например, узел может указать, что прерывания потока превратить грубые безотлагательно, однако нельзя указать обратное.</span><span class="sxs-lookup"><span data-stu-id="d5526-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="d5526-137">В следующей таблице описаны допустимые `action` значения для допустимых `operation` значения.</span><span class="sxs-lookup"><span data-stu-id="d5526-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="d5526-138">Значение для`operation`</span><span class="sxs-lookup"><span data-stu-id="d5526-138">Value for `operation`</span></span>|<span data-ttu-id="d5526-139">Допустимые значения`action`</span><span class="sxs-lookup"><span data-stu-id="d5526-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="d5526-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d5526-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="d5526-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d5526-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="d5526-142">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="d5526-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="d5526-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5526-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d5526-144">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5526-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d5526-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-145">-   eExitProcess</span></span><br /><span data-ttu-id="d5526-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="d5526-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d5526-148">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d5526-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d5526-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d5526-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="d5526-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5526-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="d5526-151">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5526-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="d5526-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-152">-   eExitProcess</span></span><br /><span data-ttu-id="d5526-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="d5526-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d5526-155">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d5526-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="d5526-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d5526-156">OPR_ProcessExit</span></span>|<span data-ttu-id="d5526-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-157">-   eExitProcess</span></span><br /><span data-ttu-id="d5526-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="d5526-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="d5526-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="d5526-160">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="d5526-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5526-161">Требования</span><span class="sxs-lookup"><span data-stu-id="d5526-161">Requirements</span></span>  
 <span data-ttu-id="d5526-162">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5526-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5526-163">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5526-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5526-164">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5526-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5526-165">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5526-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5526-166">См. также</span><span class="sxs-lookup"><span data-stu-id="d5526-166">See Also</span></span>  
 [<span data-ttu-id="d5526-167">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="d5526-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="d5526-168">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="d5526-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="d5526-169">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="d5526-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d5526-170">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d5526-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
