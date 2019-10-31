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
ms.openlocfilehash: 9ef906ed5e8a6985c084741bf06b683da79c546e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140787"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="2e03c-102">Метод ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="2e03c-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="2e03c-103">Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.</span><span class="sxs-lookup"><span data-stu-id="2e03c-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e03c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e03c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e03c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e03c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="2e03c-106">окне Одно из значений [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , указывающее операцию, для которой необходимо указать действие времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="2e03c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="2e03c-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2e03c-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="2e03c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="2e03c-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="2e03c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="2e03c-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="2e03c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2e03c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="2e03c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2e03c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="2e03c-112">окне Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее действие политики, выполняемое при истечении времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="2e03c-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e03c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2e03c-113">Return Value</span></span>  
  
|<span data-ttu-id="2e03c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e03c-114">HRESULT</span></span>|<span data-ttu-id="2e03c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2e03c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e03c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e03c-116">S_OK</span></span>|<span data-ttu-id="2e03c-117">`SetActionOnTimeout` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2e03c-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="2e03c-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e03c-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e03c-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2e03c-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e03c-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e03c-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e03c-121">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2e03c-121">The call timed out.</span></span>|  
|<span data-ttu-id="2e03c-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e03c-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e03c-123">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2e03c-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e03c-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e03c-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e03c-125">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2e03c-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e03c-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e03c-126">E_FAIL</span></span>|<span data-ttu-id="2e03c-127">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2e03c-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e03c-128">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2e03c-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e03c-129">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2e03c-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2e03c-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2e03c-130">E_INVALIDARG</span></span>|<span data-ttu-id="2e03c-131">Не удается задать время ожидания для указанного `operation`или указано недопустимое значение для `operation`.</span><span class="sxs-lookup"><span data-stu-id="2e03c-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e03c-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="2e03c-132">Remarks</span></span>  
 <span data-ttu-id="2e03c-133">Значение времени ожидания может быть либо временем ожидания по умолчанию, установленным средой CLR, либо значением, заданным узлом при вызове метода [ICLRPolicyManager:: setTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2e03c-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="2e03c-134">Не все значения действий политики могут быть указаны в качестве поведения времени ожидания для операций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2e03c-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="2e03c-135">`SetActionOnTimeout` обычно используется только для эскалации поведения.</span><span class="sxs-lookup"><span data-stu-id="2e03c-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="2e03c-136">Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно.</span><span class="sxs-lookup"><span data-stu-id="2e03c-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="2e03c-137">В следующей таблице описаны допустимые значения `action` для допустимых значений `operation`.</span><span class="sxs-lookup"><span data-stu-id="2e03c-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="2e03c-138">Значение для `operation`</span><span class="sxs-lookup"><span data-stu-id="2e03c-138">Value for `operation`</span></span>|<span data-ttu-id="2e03c-139">Допустимые значения для `action`</span><span class="sxs-lookup"><span data-stu-id="2e03c-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="2e03c-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2e03c-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="2e03c-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2e03c-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="2e03c-142">-Ерудеабортсреад</span><span class="sxs-lookup"><span data-stu-id="2e03c-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="2e03c-143">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="2e03c-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2e03c-144">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="2e03c-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2e03c-145">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-145">-   eExitProcess</span></span><br /><span data-ttu-id="2e03c-146">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="2e03c-147">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2e03c-148">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="2e03c-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2e03c-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="2e03c-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="2e03c-150">-Еунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="2e03c-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2e03c-151">-Ерудеунлоадаппдомаин</span><span class="sxs-lookup"><span data-stu-id="2e03c-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2e03c-152">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-152">-   eExitProcess</span></span><br /><span data-ttu-id="2e03c-153">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="2e03c-154">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2e03c-155">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="2e03c-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2e03c-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="2e03c-156">OPR_ProcessExit</span></span>|<span data-ttu-id="2e03c-157">-Икситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-157">-   eExitProcess</span></span><br /><span data-ttu-id="2e03c-158">-Ефастекситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="2e03c-159">-Ерудикситпроцесс</span><span class="sxs-lookup"><span data-stu-id="2e03c-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2e03c-160">-Едисаблерунтиме</span><span class="sxs-lookup"><span data-stu-id="2e03c-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e03c-161">Требования</span><span class="sxs-lookup"><span data-stu-id="2e03c-161">Requirements</span></span>  
 <span data-ttu-id="2e03c-162">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e03c-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e03c-163">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2e03c-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e03c-164">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2e03c-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e03c-165">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e03c-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e03c-166">См. также</span><span class="sxs-lookup"><span data-stu-id="2e03c-166">See also</span></span>

- [<span data-ttu-id="2e03c-167">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="2e03c-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="2e03c-168">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="2e03c-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="2e03c-169">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2e03c-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2e03c-170">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="2e03c-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
