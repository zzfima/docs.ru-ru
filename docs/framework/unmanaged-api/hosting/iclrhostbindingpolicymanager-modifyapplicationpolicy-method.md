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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178101"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="d7963-102">Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="d7963-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="d7963-103">Изменяет обязательную политику для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="d7963-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7963-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7963-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d7963-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7963-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="d7963-106">(в) Идентификация сборки для изменения.</span><span class="sxs-lookup"><span data-stu-id="d7963-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="d7963-107">(в) Новая идентичность модифицированной сборки.</span><span class="sxs-lookup"><span data-stu-id="d7963-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="d7963-108">(в) Указатель на буфер, содержащий обязательные данные политики для сборки для изменения.</span><span class="sxs-lookup"><span data-stu-id="d7963-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="d7963-109">(в) Размер обязательной политики, подавивающей на замену.</span><span class="sxs-lookup"><span data-stu-id="d7963-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="d7963-110">(в) Логическое или сочетание значений [EHostBindingPolicyModifyFlags,](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) указывающих на контроль перенаправления.</span><span class="sxs-lookup"><span data-stu-id="d7963-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="d7963-111">(ваут) Указатель на буфер, содержащий новые обязательные данные политики.</span><span class="sxs-lookup"><span data-stu-id="d7963-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="d7963-112">(в, вне) Указатель на размер нового обязательного буфера политики.</span><span class="sxs-lookup"><span data-stu-id="d7963-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7963-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7963-113">Return Value</span></span>  
  
|<span data-ttu-id="d7963-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7963-114">HRESULT</span></span>|<span data-ttu-id="d7963-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d7963-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7963-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7963-116">S_OK</span></span>|<span data-ttu-id="d7963-117">Политика была успешно изменена.</span><span class="sxs-lookup"><span data-stu-id="d7963-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="d7963-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7963-118">E_INVALIDARG</span></span>|<span data-ttu-id="d7963-119">`pwzSourceAssemblyIdentity`или `pwzTargetAssemblyIdentity` была нулевая ссылка.</span><span class="sxs-lookup"><span data-stu-id="d7963-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="d7963-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d7963-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d7963-121">`pbNewApplicationPolicy` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="d7963-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="d7963-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7963-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7963-123">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d7963-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7963-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7963-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7963-125">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="d7963-125">The call timed out.</span></span>|  
|<span data-ttu-id="d7963-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7963-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7963-127">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="d7963-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7963-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7963-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7963-129">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="d7963-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7963-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7963-130">E_FAIL</span></span>|<span data-ttu-id="d7963-131">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="d7963-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7963-132">После того, как метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе.</span><span class="sxs-lookup"><span data-stu-id="d7963-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7963-133">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d7963-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7963-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7963-134">Remarks</span></span>  
 <span data-ttu-id="d7963-135">Метод `ModifyApplicationPolicy` можно вызвать дважды.</span><span class="sxs-lookup"><span data-stu-id="d7963-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="d7963-136">Первый вызов должен предоставить `pbNewApplicationPolicy` нулевую стоимость параметра.</span><span class="sxs-lookup"><span data-stu-id="d7963-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="d7963-137">Этот вызов будет возвращаться `pcbNewAppPolicySize`с необходимым значением для .</span><span class="sxs-lookup"><span data-stu-id="d7963-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="d7963-138">Второй вызов должен предоставить `pcbNewAppPolicySize`это значение для, и `pbNewApplicationPolicy`указать на буфер такого размера для .</span><span class="sxs-lookup"><span data-stu-id="d7963-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7963-139">Требования</span><span class="sxs-lookup"><span data-stu-id="d7963-139">Requirements</span></span>  
 <span data-ttu-id="d7963-140">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7963-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7963-141">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7963-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7963-142">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7963-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7963-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7963-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7963-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d7963-144">See also</span></span>

- [<span data-ttu-id="d7963-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d7963-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
