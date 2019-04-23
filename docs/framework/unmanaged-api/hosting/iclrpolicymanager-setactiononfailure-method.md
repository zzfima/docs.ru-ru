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
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117434"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="a475d-102">Метод ICLRPolicyManager::SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="a475d-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="a475d-103">Задает действие политики, которые общеязыковой среды выполнения (CLR) необходимо выполнить при возникновении указанной ошибки.</span><span class="sxs-lookup"><span data-stu-id="a475d-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a475d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a475d-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a475d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a475d-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="a475d-106">[in] Один из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения, указывающие тип сбоя, для которого требуется выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="a475d-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="a475d-107">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие действие, выполняемое при сбое.</span><span class="sxs-lookup"><span data-stu-id="a475d-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="a475d-108">Список поддерживаемых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="a475d-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a475d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a475d-109">Return Value</span></span>  
  
|<span data-ttu-id="a475d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a475d-110">HRESULT</span></span>|<span data-ttu-id="a475d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a475d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a475d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a475d-112">S_OK</span></span>|<span data-ttu-id="a475d-113">`SetActionOnFailure` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a475d-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="a475d-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a475d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a475d-115">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a475d-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a475d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a475d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a475d-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a475d-117">The call timed out.</span></span>|  
|<span data-ttu-id="a475d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a475d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a475d-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a475d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a475d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a475d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a475d-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a475d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a475d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a475d-122">E_FAIL</span></span>|<span data-ttu-id="a475d-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a475d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a475d-124">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="a475d-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a475d-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a475d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a475d-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a475d-126">E_INVALIDARG</span></span>|<span data-ttu-id="a475d-127">Невозможно задать действие политики для указанной операции или действия Недопустимая политика был указан для операции.</span><span class="sxs-lookup"><span data-stu-id="a475d-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a475d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="a475d-128">Remarks</span></span>  
 <span data-ttu-id="a475d-129">По умолчанию среда CLR создает исключение, если ей не удается выделить ресурсы, такие как память.</span><span class="sxs-lookup"><span data-stu-id="a475d-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="a475d-130">`SetActionOnFailure` позволяет узлу переопределить это поведение, указав политику действие, выполняемое в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="a475d-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="a475d-131">В следующей таблице показаны сочетания [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) и [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) поддерживаемые значения.</span><span class="sxs-lookup"><span data-stu-id="a475d-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="a475d-132">(Префикс FAIL_ исключается из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения.)</span><span class="sxs-lookup"><span data-stu-id="a475d-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="a475d-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="a475d-133">NonCriticalResource</span></span>|<span data-ttu-id="a475d-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="a475d-134">CriticalResource</span></span>|<span data-ttu-id="a475d-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="a475d-135">FatalRuntime</span></span>|<span data-ttu-id="a475d-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="a475d-136">OrphanedLock</span></span>|<span data-ttu-id="a475d-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="a475d-137">StackOverflow</span></span>|<span data-ttu-id="a475d-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="a475d-138">AccessViolation</span></span>|<span data-ttu-id="a475d-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="a475d-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="a475d-140">X</span><span class="sxs-lookup"><span data-stu-id="a475d-140">X</span></span>|<span data-ttu-id="a475d-141">X</span><span class="sxs-lookup"><span data-stu-id="a475d-141">X</span></span>||||<span data-ttu-id="a475d-142">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-142">N/A</span></span>||  
|<span data-ttu-id="a475d-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="a475d-143">eThrowException</span></span>|<span data-ttu-id="a475d-144">X</span><span class="sxs-lookup"><span data-stu-id="a475d-144">X</span></span>|<span data-ttu-id="a475d-145">X</span><span class="sxs-lookup"><span data-stu-id="a475d-145">X</span></span>||||<span data-ttu-id="a475d-146">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="a475d-147">X</span><span class="sxs-lookup"><span data-stu-id="a475d-147">X</span></span>|<span data-ttu-id="a475d-148">X</span><span class="sxs-lookup"><span data-stu-id="a475d-148">X</span></span>||||<span data-ttu-id="a475d-149">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-149">N/A</span></span>|<span data-ttu-id="a475d-150">X</span><span class="sxs-lookup"><span data-stu-id="a475d-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="a475d-151">X</span><span class="sxs-lookup"><span data-stu-id="a475d-151">X</span></span>|<span data-ttu-id="a475d-152">X</span><span class="sxs-lookup"><span data-stu-id="a475d-152">X</span></span>||||<span data-ttu-id="a475d-153">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-153">N/A</span></span>|<span data-ttu-id="a475d-154">X</span><span class="sxs-lookup"><span data-stu-id="a475d-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="a475d-155">X</span><span class="sxs-lookup"><span data-stu-id="a475d-155">X</span></span>|<span data-ttu-id="a475d-156">X</span><span class="sxs-lookup"><span data-stu-id="a475d-156">X</span></span>||<span data-ttu-id="a475d-157">X</span><span class="sxs-lookup"><span data-stu-id="a475d-157">X</span></span>||<span data-ttu-id="a475d-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-158">N/A</span></span>|<span data-ttu-id="a475d-159">X</span><span class="sxs-lookup"><span data-stu-id="a475d-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="a475d-160">X</span><span class="sxs-lookup"><span data-stu-id="a475d-160">X</span></span>|<span data-ttu-id="a475d-161">X</span><span class="sxs-lookup"><span data-stu-id="a475d-161">X</span></span>||<span data-ttu-id="a475d-162">X</span><span class="sxs-lookup"><span data-stu-id="a475d-162">X</span></span>|<span data-ttu-id="a475d-163">X</span><span class="sxs-lookup"><span data-stu-id="a475d-163">X</span></span>|<span data-ttu-id="a475d-164">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-164">N/A</span></span>|<span data-ttu-id="a475d-165">X</span><span class="sxs-lookup"><span data-stu-id="a475d-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="a475d-166">X</span><span class="sxs-lookup"><span data-stu-id="a475d-166">X</span></span>|<span data-ttu-id="a475d-167">X</span><span class="sxs-lookup"><span data-stu-id="a475d-167">X</span></span>||<span data-ttu-id="a475d-168">X</span><span class="sxs-lookup"><span data-stu-id="a475d-168">X</span></span>|<span data-ttu-id="a475d-169">X</span><span class="sxs-lookup"><span data-stu-id="a475d-169">X</span></span>|<span data-ttu-id="a475d-170">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-170">N/A</span></span>|<span data-ttu-id="a475d-171">X</span><span class="sxs-lookup"><span data-stu-id="a475d-171">X</span></span>|  
|<span data-ttu-id="a475d-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="a475d-172">eFastExitProcess</span></span>|<span data-ttu-id="a475d-173">X</span><span class="sxs-lookup"><span data-stu-id="a475d-173">X</span></span>|<span data-ttu-id="a475d-174">X</span><span class="sxs-lookup"><span data-stu-id="a475d-174">X</span></span>||<span data-ttu-id="a475d-175">X</span><span class="sxs-lookup"><span data-stu-id="a475d-175">X</span></span>|<span data-ttu-id="a475d-176">X</span><span class="sxs-lookup"><span data-stu-id="a475d-176">X</span></span>|<span data-ttu-id="a475d-177">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="a475d-178">X</span><span class="sxs-lookup"><span data-stu-id="a475d-178">X</span></span>|<span data-ttu-id="a475d-179">X</span><span class="sxs-lookup"><span data-stu-id="a475d-179">X</span></span>|<span data-ttu-id="a475d-180">X</span><span class="sxs-lookup"><span data-stu-id="a475d-180">X</span></span>|<span data-ttu-id="a475d-181">X</span><span class="sxs-lookup"><span data-stu-id="a475d-181">X</span></span>|<span data-ttu-id="a475d-182">X</span><span class="sxs-lookup"><span data-stu-id="a475d-182">X</span></span>|<span data-ttu-id="a475d-183">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="a475d-184">X</span><span class="sxs-lookup"><span data-stu-id="a475d-184">X</span></span>|<span data-ttu-id="a475d-185">X</span><span class="sxs-lookup"><span data-stu-id="a475d-185">X</span></span>|<span data-ttu-id="a475d-186">X</span><span class="sxs-lookup"><span data-stu-id="a475d-186">X</span></span>|<span data-ttu-id="a475d-187">X</span><span class="sxs-lookup"><span data-stu-id="a475d-187">X</span></span>|<span data-ttu-id="a475d-188">X</span><span class="sxs-lookup"><span data-stu-id="a475d-188">X</span></span>|<span data-ttu-id="a475d-189">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a475d-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="a475d-190">Требования</span><span class="sxs-lookup"><span data-stu-id="a475d-190">Requirements</span></span>  
 <span data-ttu-id="a475d-191">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a475d-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a475d-192">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a475d-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a475d-193">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a475d-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a475d-194">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a475d-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a475d-195">См. также</span><span class="sxs-lookup"><span data-stu-id="a475d-195">See also</span></span>

- [<span data-ttu-id="a475d-196">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="a475d-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a475d-197">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="a475d-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="a475d-198">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a475d-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a475d-199">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a475d-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
