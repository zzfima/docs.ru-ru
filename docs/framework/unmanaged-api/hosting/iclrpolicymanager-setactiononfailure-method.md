---
title: "Метод ICLRPolicyManager::SetActionOnFailure"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5dc8e27ed1a5701886c3583a7515e4212f490208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="8882e-102">Метод ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="8882e-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="8882e-103">Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), если указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="8882e-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8882e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8882e-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8882e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8882e-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="8882e-106">[in] Один из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения, указывающие тип сбоя, для которого требуется выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="8882e-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="8882e-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее действие, предпринимаемое при возникновении сбоя.</span><span class="sxs-lookup"><span data-stu-id="8882e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="8882e-108">Список поддерживаемых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="8882e-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8882e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8882e-109">Return Value</span></span>  
  
|<span data-ttu-id="8882e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8882e-110">HRESULT</span></span>|<span data-ttu-id="8882e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8882e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8882e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8882e-112">S_OK</span></span>|<span data-ttu-id="8882e-113">`SetActionOnFailure`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8882e-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="8882e-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8882e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8882e-115">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8882e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8882e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8882e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8882e-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8882e-117">The call timed out.</span></span>|  
|<span data-ttu-id="8882e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8882e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8882e-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8882e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8882e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8882e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8882e-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8882e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8882e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8882e-122">E_FAIL</span></span>|<span data-ttu-id="8882e-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8882e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8882e-124">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8882e-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8882e-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8882e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8882e-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8882e-126">E_INVALIDARG</span></span>|<span data-ttu-id="8882e-127">Невозможно задать действие политики для указанной операции или для операции указано недопустимое действие политики.</span><span class="sxs-lookup"><span data-stu-id="8882e-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8882e-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="8882e-128">Remarks</span></span>  
 <span data-ttu-id="8882e-129">По умолчанию среда CLR создает исключение, если ему не удалось выделить ресурс, например памяти.</span><span class="sxs-lookup"><span data-stu-id="8882e-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="8882e-130">`SetActionOnFailure`предоставляет узлу возможность переопределить это поведение, задав действие политики при сбое.</span><span class="sxs-lookup"><span data-stu-id="8882e-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="8882e-131">В следующей таблице показаны сочетания [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) и [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) поддерживаемые значения.</span><span class="sxs-lookup"><span data-stu-id="8882e-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="8882e-132">(Опущена префикс FAIL_ [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значений.)</span><span class="sxs-lookup"><span data-stu-id="8882e-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="8882e-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="8882e-133">NonCriticalResource</span></span>|<span data-ttu-id="8882e-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="8882e-134">CriticalResource</span></span>|<span data-ttu-id="8882e-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="8882e-135">FatalRuntime</span></span>|<span data-ttu-id="8882e-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="8882e-136">OrphanedLock</span></span>|<span data-ttu-id="8882e-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="8882e-137">StackOverflow</span></span>|<span data-ttu-id="8882e-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="8882e-138">AccessViolation</span></span>|<span data-ttu-id="8882e-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="8882e-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="8882e-140">X</span><span class="sxs-lookup"><span data-stu-id="8882e-140">X</span></span>|<span data-ttu-id="8882e-141">X</span><span class="sxs-lookup"><span data-stu-id="8882e-141">X</span></span>||||<span data-ttu-id="8882e-142">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-142">N/A</span></span>||  
|<span data-ttu-id="8882e-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="8882e-143">eThrowException</span></span>|<span data-ttu-id="8882e-144">X</span><span class="sxs-lookup"><span data-stu-id="8882e-144">X</span></span>|<span data-ttu-id="8882e-145">X</span><span class="sxs-lookup"><span data-stu-id="8882e-145">X</span></span>||||<span data-ttu-id="8882e-146">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="8882e-147">X</span><span class="sxs-lookup"><span data-stu-id="8882e-147">X</span></span>|<span data-ttu-id="8882e-148">X</span><span class="sxs-lookup"><span data-stu-id="8882e-148">X</span></span>||||<span data-ttu-id="8882e-149">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-149">N/A</span></span>|<span data-ttu-id="8882e-150">X</span><span class="sxs-lookup"><span data-stu-id="8882e-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="8882e-151">X</span><span class="sxs-lookup"><span data-stu-id="8882e-151">X</span></span>|<span data-ttu-id="8882e-152">X</span><span class="sxs-lookup"><span data-stu-id="8882e-152">X</span></span>||||<span data-ttu-id="8882e-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-153">N/A</span></span>|<span data-ttu-id="8882e-154">X</span><span class="sxs-lookup"><span data-stu-id="8882e-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="8882e-155">X</span><span class="sxs-lookup"><span data-stu-id="8882e-155">X</span></span>|<span data-ttu-id="8882e-156">X</span><span class="sxs-lookup"><span data-stu-id="8882e-156">X</span></span>||<span data-ttu-id="8882e-157">X</span><span class="sxs-lookup"><span data-stu-id="8882e-157">X</span></span>||<span data-ttu-id="8882e-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-158">N/A</span></span>|<span data-ttu-id="8882e-159">X</span><span class="sxs-lookup"><span data-stu-id="8882e-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="8882e-160">X</span><span class="sxs-lookup"><span data-stu-id="8882e-160">X</span></span>|<span data-ttu-id="8882e-161">X</span><span class="sxs-lookup"><span data-stu-id="8882e-161">X</span></span>||<span data-ttu-id="8882e-162">X</span><span class="sxs-lookup"><span data-stu-id="8882e-162">X</span></span>|<span data-ttu-id="8882e-163">X</span><span class="sxs-lookup"><span data-stu-id="8882e-163">X</span></span>|<span data-ttu-id="8882e-164">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-164">N/A</span></span>|<span data-ttu-id="8882e-165">X</span><span class="sxs-lookup"><span data-stu-id="8882e-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="8882e-166">X</span><span class="sxs-lookup"><span data-stu-id="8882e-166">X</span></span>|<span data-ttu-id="8882e-167">X</span><span class="sxs-lookup"><span data-stu-id="8882e-167">X</span></span>||<span data-ttu-id="8882e-168">X</span><span class="sxs-lookup"><span data-stu-id="8882e-168">X</span></span>|<span data-ttu-id="8882e-169">X</span><span class="sxs-lookup"><span data-stu-id="8882e-169">X</span></span>|<span data-ttu-id="8882e-170">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-170">N/A</span></span>|<span data-ttu-id="8882e-171">X</span><span class="sxs-lookup"><span data-stu-id="8882e-171">X</span></span>|  
|<span data-ttu-id="8882e-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="8882e-172">eFastExitProcess</span></span>|<span data-ttu-id="8882e-173">X</span><span class="sxs-lookup"><span data-stu-id="8882e-173">X</span></span>|<span data-ttu-id="8882e-174">X</span><span class="sxs-lookup"><span data-stu-id="8882e-174">X</span></span>||<span data-ttu-id="8882e-175">X</span><span class="sxs-lookup"><span data-stu-id="8882e-175">X</span></span>|<span data-ttu-id="8882e-176">X</span><span class="sxs-lookup"><span data-stu-id="8882e-176">X</span></span>|<span data-ttu-id="8882e-177">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="8882e-178">X</span><span class="sxs-lookup"><span data-stu-id="8882e-178">X</span></span>|<span data-ttu-id="8882e-179">X</span><span class="sxs-lookup"><span data-stu-id="8882e-179">X</span></span>|<span data-ttu-id="8882e-180">X</span><span class="sxs-lookup"><span data-stu-id="8882e-180">X</span></span>|<span data-ttu-id="8882e-181">X</span><span class="sxs-lookup"><span data-stu-id="8882e-181">X</span></span>|<span data-ttu-id="8882e-182">X</span><span class="sxs-lookup"><span data-stu-id="8882e-182">X</span></span>|<span data-ttu-id="8882e-183">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="8882e-184">X</span><span class="sxs-lookup"><span data-stu-id="8882e-184">X</span></span>|<span data-ttu-id="8882e-185">X</span><span class="sxs-lookup"><span data-stu-id="8882e-185">X</span></span>|<span data-ttu-id="8882e-186">X</span><span class="sxs-lookup"><span data-stu-id="8882e-186">X</span></span>|<span data-ttu-id="8882e-187">X</span><span class="sxs-lookup"><span data-stu-id="8882e-187">X</span></span>|<span data-ttu-id="8882e-188">X</span><span class="sxs-lookup"><span data-stu-id="8882e-188">X</span></span>|<span data-ttu-id="8882e-189">Н/Д</span><span class="sxs-lookup"><span data-stu-id="8882e-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="8882e-190">Требования</span><span class="sxs-lookup"><span data-stu-id="8882e-190">Requirements</span></span>  
 <span data-ttu-id="8882e-191">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8882e-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8882e-192">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8882e-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8882e-193">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8882e-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8882e-194">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8882e-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8882e-195">См. также</span><span class="sxs-lookup"><span data-stu-id="8882e-195">See Also</span></span>  
 [<span data-ttu-id="8882e-196">EClrFailure-перечисление</span><span class="sxs-lookup"><span data-stu-id="8882e-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="8882e-197">EPolicyAction-перечисление</span><span class="sxs-lookup"><span data-stu-id="8882e-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="8882e-198">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8882e-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8882e-199">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="8882e-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
