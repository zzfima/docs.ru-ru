---
title: "Метод ICLRPolicyManager::SetActionOnTimeout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 924a8a64fb698ec0e78397ad791f445297c0fee6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="10a8e-102">Метод ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="10a8e-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="10a8e-103">Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), после истечения указанного времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="10a8e-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10a8e-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10a8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10a8e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="10a8e-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывает, что операция, для которого требуется задать время ожидания действия.</span><span class="sxs-lookup"><span data-stu-id="10a8e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="10a8e-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="10a8e-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="10a8e-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="10a8e-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="10a8e-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="10a8e-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="10a8e-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="10a8e-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="10a8e-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="10a8e-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="10a8e-112">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее политику действие, выполняемое после истечения времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="10a8e-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10a8e-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10a8e-113">Return Value</span></span>  
  
|<span data-ttu-id="10a8e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10a8e-114">HRESULT</span></span>|<span data-ttu-id="10a8e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="10a8e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10a8e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="10a8e-116">S_OK</span></span>|<span data-ttu-id="10a8e-117">`SetActionOnTimeout`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="10a8e-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="10a8e-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10a8e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10a8e-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="10a8e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10a8e-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10a8e-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10a8e-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="10a8e-121">The call timed out.</span></span>|  
|<span data-ttu-id="10a8e-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10a8e-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10a8e-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="10a8e-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10a8e-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10a8e-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10a8e-125">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="10a8e-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10a8e-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10a8e-126">E_FAIL</span></span>|<span data-ttu-id="10a8e-127">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="10a8e-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10a8e-128">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="10a8e-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10a8e-129">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10a8e-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="10a8e-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="10a8e-130">E_INVALIDARG</span></span>|<span data-ttu-id="10a8e-131">Невозможно задать время ожидания для указанного `operation`, или было задано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="10a8e-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a8e-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="10a8e-132">Remarks</span></span>  
 <span data-ttu-id="10a8e-133">Значение времени ожидания может быть время ожидания по умолчанию, заданное в среде CLR или значения, указанного в узле в вызове [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="10a8e-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="10a8e-134">Не все значения действий политики может быть указан как поведение времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="10a8e-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="10a8e-135">`SetActionOnTimeout`обычно используется только для повышения поведение.</span><span class="sxs-lookup"><span data-stu-id="10a8e-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="10a8e-136">Например, узел может указать, что прерывания потока превратить грубые безотлагательно, однако нельзя указать обратное.</span><span class="sxs-lookup"><span data-stu-id="10a8e-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="10a8e-137">В следующей таблице описаны допустимые `action` значения для допустимых `operation` значения.</span><span class="sxs-lookup"><span data-stu-id="10a8e-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="10a8e-138">Значение для`operation`</span><span class="sxs-lookup"><span data-stu-id="10a8e-138">Value for `operation`</span></span>|<span data-ttu-id="10a8e-139">Допустимые значения`action`</span><span class="sxs-lookup"><span data-stu-id="10a8e-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="10a8e-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="10a8e-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="10a8e-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="10a8e-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="10a8e-142">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="10a8e-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="10a8e-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="10a8e-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="10a8e-144">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="10a8e-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="10a8e-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-145">-   eExitProcess</span></span><br /><span data-ttu-id="10a8e-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="10a8e-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="10a8e-148">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="10a8e-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="10a8e-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="10a8e-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="10a8e-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="10a8e-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="10a8e-151">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="10a8e-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="10a8e-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-152">-   eExitProcess</span></span><br /><span data-ttu-id="10a8e-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="10a8e-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="10a8e-155">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="10a8e-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="10a8e-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="10a8e-156">OPR_ProcessExit</span></span>|<span data-ttu-id="10a8e-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-157">-   eExitProcess</span></span><br /><span data-ttu-id="10a8e-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="10a8e-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="10a8e-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="10a8e-160">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="10a8e-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10a8e-161">Требования</span><span class="sxs-lookup"><span data-stu-id="10a8e-161">Requirements</span></span>  
 <span data-ttu-id="10a8e-162">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a8e-163">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10a8e-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10a8e-164">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10a8e-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10a8e-165">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a8e-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a8e-166">См. также</span><span class="sxs-lookup"><span data-stu-id="10a8e-166">See Also</span></span>  
 [<span data-ttu-id="10a8e-167">EClrOperation-перечисление</span><span class="sxs-lookup"><span data-stu-id="10a8e-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="10a8e-168">EPolicyAction-перечисление</span><span class="sxs-lookup"><span data-stu-id="10a8e-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="10a8e-169">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="10a8e-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="10a8e-170">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="10a8e-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
