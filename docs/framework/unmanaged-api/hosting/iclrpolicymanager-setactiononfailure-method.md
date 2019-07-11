---
title: Метод ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76f064d1683615ef8f665cf1facaa31d61b294a5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759594"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="faf9c-102">Метод ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="faf9c-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="faf9c-103">Задает действие политики, которые общеязыковой среды выполнения (CLR) необходимо выполнить при возникновении указанной ошибки.</span><span class="sxs-lookup"><span data-stu-id="faf9c-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="faf9c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="faf9c-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="faf9c-106">[in] Один из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения, указывающие тип сбоя, для которого требуется выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="faf9c-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="faf9c-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие действие, выполняемое при сбое.</span><span class="sxs-lookup"><span data-stu-id="faf9c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="faf9c-108">Список поддерживаемых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="faf9c-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faf9c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="faf9c-109">Return Value</span></span>  
  
|<span data-ttu-id="faf9c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faf9c-110">HRESULT</span></span>|<span data-ttu-id="faf9c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="faf9c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faf9c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="faf9c-112">S_OK</span></span>|<span data-ttu-id="faf9c-113">`SetActionOnFailure` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="faf9c-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="faf9c-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faf9c-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faf9c-115">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="faf9c-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faf9c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faf9c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faf9c-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="faf9c-117">The call timed out.</span></span>|  
|<span data-ttu-id="faf9c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faf9c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faf9c-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="faf9c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faf9c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faf9c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faf9c-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="faf9c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faf9c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faf9c-122">E_FAIL</span></span>|<span data-ttu-id="faf9c-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="faf9c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faf9c-124">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="faf9c-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faf9c-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="faf9c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="faf9c-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="faf9c-126">E_INVALIDARG</span></span>|<span data-ttu-id="faf9c-127">Невозможно задать действие политики для указанной операции или действия Недопустимая политика был указан для операции.</span><span class="sxs-lookup"><span data-stu-id="faf9c-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf9c-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="faf9c-128">Remarks</span></span>  
 <span data-ttu-id="faf9c-129">По умолчанию среда CLR создает исключение, если ей не удается выделить ресурсы, такие как память.</span><span class="sxs-lookup"><span data-stu-id="faf9c-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="faf9c-130">`SetActionOnFailure` позволяет узлу переопределить это поведение, указав политику действие, выполняемое в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="faf9c-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="faf9c-131">В следующей таблице показаны сочетания [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) и [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) поддерживаемые значения.</span><span class="sxs-lookup"><span data-stu-id="faf9c-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="faf9c-132">(Префикс FAIL_ исключается из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения.)</span><span class="sxs-lookup"><span data-stu-id="faf9c-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="faf9c-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="faf9c-133">NonCriticalResource</span></span>|<span data-ttu-id="faf9c-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="faf9c-134">CriticalResource</span></span>|<span data-ttu-id="faf9c-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="faf9c-135">FatalRuntime</span></span>|<span data-ttu-id="faf9c-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="faf9c-136">OrphanedLock</span></span>|<span data-ttu-id="faf9c-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="faf9c-137">StackOverflow</span></span>|<span data-ttu-id="faf9c-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="faf9c-138">AccessViolation</span></span>|<span data-ttu-id="faf9c-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="faf9c-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="faf9c-140">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-140">X</span></span>|<span data-ttu-id="faf9c-141">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-141">X</span></span>||||<span data-ttu-id="faf9c-142">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-142">N/A</span></span>||  
|<span data-ttu-id="faf9c-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="faf9c-143">eThrowException</span></span>|<span data-ttu-id="faf9c-144">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-144">X</span></span>|<span data-ttu-id="faf9c-145">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-145">X</span></span>||||<span data-ttu-id="faf9c-146">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="faf9c-147">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-147">X</span></span>|<span data-ttu-id="faf9c-148">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-148">X</span></span>||||<span data-ttu-id="faf9c-149">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-149">N/A</span></span>|<span data-ttu-id="faf9c-150">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="faf9c-151">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-151">X</span></span>|<span data-ttu-id="faf9c-152">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-152">X</span></span>||||<span data-ttu-id="faf9c-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-153">N/A</span></span>|<span data-ttu-id="faf9c-154">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="faf9c-155">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-155">X</span></span>|<span data-ttu-id="faf9c-156">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-156">X</span></span>||<span data-ttu-id="faf9c-157">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-157">X</span></span>||<span data-ttu-id="faf9c-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-158">N/A</span></span>|<span data-ttu-id="faf9c-159">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="faf9c-160">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-160">X</span></span>|<span data-ttu-id="faf9c-161">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-161">X</span></span>||<span data-ttu-id="faf9c-162">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-162">X</span></span>|<span data-ttu-id="faf9c-163">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-163">X</span></span>|<span data-ttu-id="faf9c-164">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-164">N/A</span></span>|<span data-ttu-id="faf9c-165">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="faf9c-166">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-166">X</span></span>|<span data-ttu-id="faf9c-167">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-167">X</span></span>||<span data-ttu-id="faf9c-168">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-168">X</span></span>|<span data-ttu-id="faf9c-169">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-169">X</span></span>|<span data-ttu-id="faf9c-170">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-170">N/A</span></span>|<span data-ttu-id="faf9c-171">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-171">X</span></span>|  
|<span data-ttu-id="faf9c-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="faf9c-172">eFastExitProcess</span></span>|<span data-ttu-id="faf9c-173">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-173">X</span></span>|<span data-ttu-id="faf9c-174">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-174">X</span></span>||<span data-ttu-id="faf9c-175">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-175">X</span></span>|<span data-ttu-id="faf9c-176">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-176">X</span></span>|<span data-ttu-id="faf9c-177">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="faf9c-178">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-178">X</span></span>|<span data-ttu-id="faf9c-179">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-179">X</span></span>|<span data-ttu-id="faf9c-180">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-180">X</span></span>|<span data-ttu-id="faf9c-181">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-181">X</span></span>|<span data-ttu-id="faf9c-182">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-182">X</span></span>|<span data-ttu-id="faf9c-183">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="faf9c-184">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-184">X</span></span>|<span data-ttu-id="faf9c-185">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-185">X</span></span>|<span data-ttu-id="faf9c-186">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-186">X</span></span>|<span data-ttu-id="faf9c-187">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-187">X</span></span>|<span data-ttu-id="faf9c-188">X</span><span class="sxs-lookup"><span data-stu-id="faf9c-188">X</span></span>|<span data-ttu-id="faf9c-189">Н/Д</span><span class="sxs-lookup"><span data-stu-id="faf9c-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="faf9c-190">Требования</span><span class="sxs-lookup"><span data-stu-id="faf9c-190">Requirements</span></span>  
 <span data-ttu-id="faf9c-191">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf9c-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf9c-192">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="faf9c-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faf9c-193">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="faf9c-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faf9c-194">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf9c-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf9c-195">См. также</span><span class="sxs-lookup"><span data-stu-id="faf9c-195">See also</span></span>

- [<span data-ttu-id="faf9c-196">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="faf9c-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="faf9c-197">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="faf9c-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="faf9c-198">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="faf9c-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="faf9c-199">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="faf9c-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
