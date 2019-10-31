---
title: Метод ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141180"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="ccbfb-102">Метод ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="ccbfb-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="ccbfb-103">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccbfb-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccbfb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccbfb-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="ccbfb-106">окне Ссылка на сборку перед вычислением политики.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="ccbfb-107">окне Указатель на буфер, содержащий данные политики.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="ccbfb-108">окне Размер буфера `pbApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="ccbfb-109">заполняет Ссылка на сборку после вычисления новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="ccbfb-110">[вход, выход] Указатель на размер буфера ссылки идентификации сборки после вычисления новых данных политики.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="ccbfb-111">заполняет Указатель на логическое или сочетание значений [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) , указывающих, какие политики были применены.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccbfb-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ccbfb-112">Return Value</span></span>  
  
|<span data-ttu-id="ccbfb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccbfb-113">HRESULT</span></span>|<span data-ttu-id="ccbfb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ccbfb-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccbfb-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccbfb-115">S_OK</span></span>|<span data-ttu-id="ccbfb-116">Оценка успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="ccbfb-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ccbfb-117">E_INVALIDARG</span></span>|<span data-ttu-id="ccbfb-118">Либо `pwzReferenceIdentity`, либо `pbApplicationPolicy` является пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="ccbfb-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ccbfb-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ccbfb-120">`cbAppPolicySize` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="ccbfb-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccbfb-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccbfb-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccbfb-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccbfb-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccbfb-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-124">The call timed out.</span></span>|  
|<span data-ttu-id="ccbfb-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccbfb-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccbfb-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccbfb-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccbfb-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccbfb-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccbfb-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccbfb-129">E_FAIL</span></span>|<span data-ttu-id="ccbfb-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccbfb-131">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccbfb-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccbfb-133">Заметки</span><span class="sxs-lookup"><span data-stu-id="ccbfb-133">Remarks</span></span>  
 <span data-ttu-id="ccbfb-134">Метод `EvaluatePolicy` позволяет основному приложению оказывать влияние на политику привязки для поддержки требований к версии сборки, относящейся к конкретному узлу.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="ccbfb-135">Сам модуль политики остается внутри среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ccbfb-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccbfb-136">Требования</span><span class="sxs-lookup"><span data-stu-id="ccbfb-136">Requirements</span></span>  
 <span data-ttu-id="ccbfb-137">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccbfb-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccbfb-138">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ccbfb-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccbfb-139">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccbfb-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccbfb-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccbfb-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbfb-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ccbfb-141">See also</span></span>

- [<span data-ttu-id="ccbfb-142">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ccbfb-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
