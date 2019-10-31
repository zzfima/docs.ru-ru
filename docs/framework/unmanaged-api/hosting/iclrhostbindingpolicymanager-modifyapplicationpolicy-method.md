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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141074"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="790e2-102">Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="790e2-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="790e2-103">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="790e2-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="790e2-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="790e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="790e2-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="790e2-106">окне Идентификатор сборки, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="790e2-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="790e2-107">окне Новое удостоверение измененной сборки.</span><span class="sxs-lookup"><span data-stu-id="790e2-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="790e2-108">окне Указатель на буфер, содержащий данные политики привязки для изменяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="790e2-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="790e2-109">окне Размер заменяемой политики привязки.</span><span class="sxs-lookup"><span data-stu-id="790e2-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="790e2-110">окне Логическое или сочетание значений [ехостбиндингполицимодифифлагс](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) , указывающее на контроль перенаправления.</span><span class="sxs-lookup"><span data-stu-id="790e2-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="790e2-111">заполняет Указатель на буфер, содержащий новые данные политики привязки.</span><span class="sxs-lookup"><span data-stu-id="790e2-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="790e2-112">[вход, выход] Указатель на размер нового буфера политики привязки.</span><span class="sxs-lookup"><span data-stu-id="790e2-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="790e2-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="790e2-113">Return Value</span></span>  
  
|<span data-ttu-id="790e2-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="790e2-114">HRESULT</span></span>|<span data-ttu-id="790e2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="790e2-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="790e2-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="790e2-116">S_OK</span></span>|<span data-ttu-id="790e2-117">Политика успешно изменена.</span><span class="sxs-lookup"><span data-stu-id="790e2-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="790e2-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="790e2-118">E_INVALIDARG</span></span>|<span data-ttu-id="790e2-119">`pwzSourceAssemblyIdentity` или `pwzTargetAssemblyIdentity` была пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="790e2-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="790e2-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="790e2-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="790e2-121">`pbNewApplicationPolicy` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="790e2-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="790e2-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="790e2-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="790e2-123">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="790e2-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="790e2-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="790e2-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="790e2-125">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="790e2-125">The call timed out.</span></span>|  
|<span data-ttu-id="790e2-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="790e2-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="790e2-127">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="790e2-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="790e2-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="790e2-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="790e2-129">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="790e2-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="790e2-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="790e2-130">E_FAIL</span></span>|<span data-ttu-id="790e2-131">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="790e2-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="790e2-132">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="790e2-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="790e2-133">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="790e2-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790e2-134">Заметки</span><span class="sxs-lookup"><span data-stu-id="790e2-134">Remarks</span></span>  
 <span data-ttu-id="790e2-135">Метод `ModifyApplicationPolicy` можно вызывать дважды.</span><span class="sxs-lookup"><span data-stu-id="790e2-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="790e2-136">Первый вызов должен предоставить значение NULL для параметра `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="790e2-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="790e2-137">Этот вызов возвратит с требуемым значением для `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="790e2-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="790e2-138">Второй вызов должен предоставить это значение для `pcbNewAppPolicySize`и указать буфер этого размера для `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="790e2-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="790e2-139">Требования</span><span class="sxs-lookup"><span data-stu-id="790e2-139">Requirements</span></span>  
 <span data-ttu-id="790e2-140">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="790e2-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="790e2-141">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="790e2-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="790e2-142">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="790e2-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="790e2-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="790e2-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790e2-144">См. также</span><span class="sxs-lookup"><span data-stu-id="790e2-144">See also</span></span>

- [<span data-ttu-id="790e2-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="790e2-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
