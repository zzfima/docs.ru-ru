---
title: "Метод ICLRHostBindingPolicyManager::EvaluatePolicy"
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
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14f4db56529fbbb08f8f3d9adde0d4dc7a8ce045
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="bc03d-102">Метод ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="bc03d-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="bc03d-103">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="bc03d-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc03d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc03d-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc03d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc03d-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="bc03d-106">[in] Ссылка на сборку до вычисления политики.</span><span class="sxs-lookup"><span data-stu-id="bc03d-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="bc03d-107">[in] Указатель на буфер, содержащий данные о политике.</span><span class="sxs-lookup"><span data-stu-id="bc03d-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="bc03d-108">[in] Размер `pbApplicationPolicy` буфера.</span><span class="sxs-lookup"><span data-stu-id="bc03d-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="bc03d-109">[out] Ссылка на сборку после вычисления новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="bc03d-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="bc03d-110">[in, out] Указатель на размер буфера ссылку удостоверение сборки после оценки новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="bc03d-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="bc03d-111">[out] Указатель на сочетание логического или [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) значения, указывающие, какие политики были применены.</span><span class="sxs-lookup"><span data-stu-id="bc03d-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc03d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc03d-112">Return Value</span></span>  
  
|<span data-ttu-id="bc03d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc03d-113">HRESULT</span></span>|<span data-ttu-id="bc03d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bc03d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc03d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc03d-115">S_OK</span></span>|<span data-ttu-id="bc03d-116">Оценка успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="bc03d-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="bc03d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bc03d-117">E_INVALIDARG</span></span>|<span data-ttu-id="bc03d-118">Либо `pwzReferenceIdentity` или `pbApplicationPolicy` является пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="bc03d-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="bc03d-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bc03d-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bc03d-120">`cbAppPolicySize` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="bc03d-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="bc03d-121">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc03d-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc03d-122">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bc03d-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc03d-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc03d-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc03d-124">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="bc03d-124">The call timed out.</span></span>|  
|<span data-ttu-id="bc03d-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc03d-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc03d-126">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="bc03d-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc03d-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc03d-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc03d-128">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="bc03d-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc03d-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc03d-129">E_FAIL</span></span>|<span data-ttu-id="bc03d-130">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="bc03d-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc03d-131">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bc03d-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc03d-132">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bc03d-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc03d-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc03d-133">Remarks</span></span>  
 <span data-ttu-id="bc03d-134">`EvaluatePolicy` Метод предоставляет узлу возможность влиять на политику привязки для конкретного узла сборки требования к управлению версиями.</span><span class="sxs-lookup"><span data-stu-id="bc03d-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="bc03d-135">Сам обработчик политик остается внутри среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bc03d-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc03d-136">Требования</span><span class="sxs-lookup"><span data-stu-id="bc03d-136">Requirements</span></span>  
 <span data-ttu-id="bc03d-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc03d-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc03d-138">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc03d-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc03d-139">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc03d-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc03d-140">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc03d-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc03d-141">См. также</span><span class="sxs-lookup"><span data-stu-id="bc03d-141">See Also</span></span>  
 [<span data-ttu-id="bc03d-142">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="bc03d-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
