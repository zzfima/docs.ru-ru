---
title: Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a9e438e6dd436303cd6f7aa60c779179b5d3c04
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779673"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="7c724-102">Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="7c724-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="7c724-103">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="7c724-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c724-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c724-104">Syntax</span></span>  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c724-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c724-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="7c724-106">[in] Удостоверение сборки для изменения.</span><span class="sxs-lookup"><span data-stu-id="7c724-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="7c724-107">[in] Новый идентификатор измененной сборке.</span><span class="sxs-lookup"><span data-stu-id="7c724-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="7c724-108">[in] Указатель на буфер, содержащий данные о политике привязки для сборки для изменения.</span><span class="sxs-lookup"><span data-stu-id="7c724-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="7c724-109">[in] Размер политику привязки заменяемого.</span><span class="sxs-lookup"><span data-stu-id="7c724-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="7c724-110">[in] Сочетание логического или [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) значения, связанным с управлением перенаправления.</span><span class="sxs-lookup"><span data-stu-id="7c724-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="7c724-111">[out] Указатель на буфер, содержащий новые данные о политике привязки.</span><span class="sxs-lookup"><span data-stu-id="7c724-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="7c724-112">[in, out] Указатель на размер буфера новой политики привязки.</span><span class="sxs-lookup"><span data-stu-id="7c724-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c724-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7c724-113">Return Value</span></span>  
  
|<span data-ttu-id="7c724-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c724-114">HRESULT</span></span>|<span data-ttu-id="7c724-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7c724-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c724-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c724-116">S_OK</span></span>|<span data-ttu-id="7c724-117">Политика была успешно изменена.</span><span class="sxs-lookup"><span data-stu-id="7c724-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="7c724-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7c724-118">E_INVALIDARG</span></span>|<span data-ttu-id="7c724-119">`pwzSourceAssemblyIdentity` или `pwzTargetAssemblyIdentity` был ссылкой на null.</span><span class="sxs-lookup"><span data-stu-id="7c724-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="7c724-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7c724-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7c724-121">`pbNewApplicationPolicy` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="7c724-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="7c724-122">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c724-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c724-123">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7c724-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c724-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c724-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c724-125">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7c724-125">The call timed out.</span></span>|  
|<span data-ttu-id="7c724-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c724-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c724-127">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7c724-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c724-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c724-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c724-129">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7c724-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c724-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c724-130">E_FAIL</span></span>|<span data-ttu-id="7c724-131">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="7c724-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c724-132">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="7c724-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c724-133">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c724-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c724-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c724-134">Remarks</span></span>  
 <span data-ttu-id="7c724-135">`ModifyApplicationPolicy` Метод может вызываться дважды.</span><span class="sxs-lookup"><span data-stu-id="7c724-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="7c724-136">Первый вызов должен предоставить значение null для `pbNewApplicationPolicy` параметра.</span><span class="sxs-lookup"><span data-stu-id="7c724-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="7c724-137">Этот вызов вернет со значением, необходимые для `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="7c724-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="7c724-138">Второй вызов должен указывать это значение для `pcbNewAppPolicySize`и выберите пункт буфера этого размера для `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="7c724-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c724-139">Требования</span><span class="sxs-lookup"><span data-stu-id="7c724-139">Requirements</span></span>  
 <span data-ttu-id="7c724-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c724-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c724-141">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c724-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c724-142">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c724-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c724-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c724-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c724-144">См. также</span><span class="sxs-lookup"><span data-stu-id="7c724-144">See also</span></span>

- [<span data-ttu-id="7c724-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7c724-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
