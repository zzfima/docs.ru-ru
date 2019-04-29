---
title: Метод ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30ab869ed6b06f5c9e53d819e20d3307ccc0e8f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639000"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="c9391-102">Метод ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="c9391-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="c9391-103">Задает действие политики, которые среда CLR (CLR) необходимо выполнить после истечения указанного времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="c9391-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9391-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9391-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9391-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9391-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="c9391-106">[in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значений, указывающее операцию, для которого требуется задать время ожидания действия.</span><span class="sxs-lookup"><span data-stu-id="c9391-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="c9391-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c9391-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="c9391-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="c9391-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="c9391-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="c9391-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="c9391-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="c9391-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="c9391-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="c9391-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="c9391-112">[in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающий действие политики, выполняемое после истечения времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="c9391-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9391-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c9391-113">Return Value</span></span>  
  
|<span data-ttu-id="c9391-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9391-114">HRESULT</span></span>|<span data-ttu-id="c9391-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c9391-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9391-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9391-116">S_OK</span></span>|<span data-ttu-id="c9391-117">`SetActionOnTimeout` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c9391-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="c9391-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9391-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9391-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c9391-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9391-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9391-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9391-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c9391-121">The call timed out.</span></span>|  
|<span data-ttu-id="c9391-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9391-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9391-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c9391-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9391-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9391-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9391-125">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c9391-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9391-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9391-126">E_FAIL</span></span>|<span data-ttu-id="c9391-127">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c9391-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9391-128">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="c9391-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9391-129">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9391-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c9391-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c9391-130">E_INVALIDARG</span></span>|<span data-ttu-id="c9391-131">Невозможно задать время ожидания для указанного `operation`, или задано недопустимое значение `operation`.</span><span class="sxs-lookup"><span data-stu-id="c9391-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9391-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9391-132">Remarks</span></span>  
 <span data-ttu-id="c9391-133">Значение времени ожидания может быть либо время ожидания по умолчанию, заданное в среде CLR, либо значение, заданное приложением при вызове [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c9391-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="c9391-134">Не все значения действия политики можно указать как поведение времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c9391-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="c9391-135">`SetActionOnTimeout` обычно используется только для того, чтобы расширить поведение.</span><span class="sxs-lookup"><span data-stu-id="c9391-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="c9391-136">Например, узел может указать, что преобразовать прерывания потока в грубое отменой потоков, но не может.</span><span class="sxs-lookup"><span data-stu-id="c9391-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="c9391-137">В следующей таблице описываются допустимые `action` значений в параметре допустимым `operation` значения.</span><span class="sxs-lookup"><span data-stu-id="c9391-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="c9391-138">Значение для `operation`</span><span class="sxs-lookup"><span data-stu-id="c9391-138">Value for `operation`</span></span>|<span data-ttu-id="c9391-139">Допустимые значения для `action`</span><span class="sxs-lookup"><span data-stu-id="c9391-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="c9391-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="c9391-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="c9391-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="c9391-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="c9391-142">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="c9391-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="c9391-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="c9391-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="c9391-144">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="c9391-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="c9391-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-145">-   eExitProcess</span></span><br /><span data-ttu-id="c9391-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="c9391-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="c9391-148">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="c9391-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="c9391-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="c9391-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="c9391-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="c9391-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="c9391-151">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="c9391-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="c9391-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-152">-   eExitProcess</span></span><br /><span data-ttu-id="c9391-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="c9391-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="c9391-155">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="c9391-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="c9391-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="c9391-156">OPR_ProcessExit</span></span>|<span data-ttu-id="c9391-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-157">-   eExitProcess</span></span><br /><span data-ttu-id="c9391-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="c9391-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="c9391-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="c9391-160">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="c9391-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9391-161">Требования</span><span class="sxs-lookup"><span data-stu-id="c9391-161">Requirements</span></span>  
 <span data-ttu-id="c9391-162">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9391-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9391-163">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9391-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9391-164">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9391-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9391-165">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9391-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9391-166">См. также</span><span class="sxs-lookup"><span data-stu-id="c9391-166">See also</span></span>

- [<span data-ttu-id="c9391-167">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="c9391-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="c9391-168">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="c9391-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="c9391-169">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c9391-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c9391-170">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c9391-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
