---
title: "Метод ICLRPolicyManager::SetDefaultAction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 751853aaf4322c15b44bb9b912d293a081c24ba8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="978e8-102">Метод ICLRPolicyManager::SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="978e8-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="978e8-103">Задает действие политики, которое общеязыковой среды выполнения (CLR), выполняемое при возникновении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="978e8-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="978e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="978e8-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="978e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="978e8-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="978e8-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающий действие, для которых CLR можно настроить поведение.</span><span class="sxs-lookup"><span data-stu-id="978e8-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="978e8-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие действие политики CLR займет `operation` происходит.</span><span class="sxs-lookup"><span data-stu-id="978e8-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="978e8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="978e8-108">Return Value</span></span>  
  
|<span data-ttu-id="978e8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="978e8-109">HRESULT</span></span>|<span data-ttu-id="978e8-110">Описание</span><span class="sxs-lookup"><span data-stu-id="978e8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="978e8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="978e8-111">S_OK</span></span>|<span data-ttu-id="978e8-112">`SetDefaultAction`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="978e8-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="978e8-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="978e8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="978e8-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="978e8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="978e8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="978e8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="978e8-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="978e8-116">The call timed out.</span></span>|  
|<span data-ttu-id="978e8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="978e8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="978e8-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="978e8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="978e8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="978e8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="978e8-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="978e8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="978e8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="978e8-121">E_FAIL</span></span>|<span data-ttu-id="978e8-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="978e8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="978e8-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="978e8-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="978e8-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="978e8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="978e8-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="978e8-125">E_INVALIDARG</span></span>|<span data-ttu-id="978e8-126">Недопустимый `action` был указан для `operation`, или было задано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="978e8-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="978e8-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="978e8-127">Remarks</span></span>  
 <span data-ttu-id="978e8-128">Не все значения действий политики можно указать в качестве поведения по умолчанию для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="978e8-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="978e8-129">`SetDefaultAction`обычно используется только для повышения поведение.</span><span class="sxs-lookup"><span data-stu-id="978e8-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="978e8-130">Например, узел может указать, что прерывания потока превратить грубые безотлагательно, однако нельзя указать обратное.</span><span class="sxs-lookup"><span data-stu-id="978e8-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="978e8-131">В следующей таблице описаны допустимые `action` значения для каждого возможного `operation` значение.</span><span class="sxs-lookup"><span data-stu-id="978e8-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="978e8-132">Значение для`operation`</span><span class="sxs-lookup"><span data-stu-id="978e8-132">Value for `operation`</span></span>|<span data-ttu-id="978e8-133">Допустимые значения`action`</span><span class="sxs-lookup"><span data-stu-id="978e8-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="978e8-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="978e8-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="978e8-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="978e8-135">-   eAbortThread</span></span><br /><span data-ttu-id="978e8-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="978e8-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="978e8-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-139">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="978e8-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="978e8-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="978e8-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="978e8-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="978e8-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="978e8-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="978e8-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-148">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="978e8-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="978e8-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="978e8-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-155">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="978e8-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="978e8-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="978e8-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-161">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="978e8-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="978e8-165">OPR_ProcessExit</span></span>|<span data-ttu-id="978e8-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-166">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="978e8-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="978e8-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="978e8-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="978e8-171">-   eNoAction</span></span><br /><span data-ttu-id="978e8-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="978e8-172">-   eAbortThread</span></span><br /><span data-ttu-id="978e8-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="978e8-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="978e8-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="978e8-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="978e8-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-176">-   eExitProcess</span></span><br /><span data-ttu-id="978e8-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="978e8-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="978e8-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="978e8-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="978e8-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="978e8-180">Требования</span><span class="sxs-lookup"><span data-stu-id="978e8-180">Requirements</span></span>  
 <span data-ttu-id="978e8-181">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="978e8-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="978e8-182">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="978e8-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="978e8-183">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="978e8-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="978e8-184">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="978e8-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978e8-185">См. также</span><span class="sxs-lookup"><span data-stu-id="978e8-185">See Also</span></span>  
 [<span data-ttu-id="978e8-186">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="978e8-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="978e8-187">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="978e8-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="978e8-188">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="978e8-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
