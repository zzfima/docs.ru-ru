---
title: Метод ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141038"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="0fc70-102">Метод ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="0fc70-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="0fc70-103">Указывает, какие категории управляемых типов и членов следует блокировать при выполнении в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="0fc70-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fc70-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fc70-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fc70-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="0fc70-106">окне Сочетание значений [еапикатегориес](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) , указывающих, какие категории управляемых типов и членов должны блокироваться в коде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="0fc70-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fc70-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0fc70-107">Return Value</span></span>  
  
|<span data-ttu-id="0fc70-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fc70-108">HRESULT</span></span>|<span data-ttu-id="0fc70-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0fc70-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0fc70-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0fc70-110">S_OK</span></span>|<span data-ttu-id="0fc70-111">`SetProtectedCategories` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="0fc70-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="0fc70-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0fc70-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0fc70-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0fc70-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0fc70-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0fc70-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0fc70-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="0fc70-115">The call timed out.</span></span>|  
|<span data-ttu-id="0fc70-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0fc70-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0fc70-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="0fc70-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0fc70-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0fc70-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0fc70-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="0fc70-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0fc70-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0fc70-120">E_FAIL</span></span>|<span data-ttu-id="0fc70-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0fc70-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0fc70-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0fc70-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0fc70-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0fc70-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fc70-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="0fc70-124">Remarks</span></span>  
 <span data-ttu-id="0fc70-125">Каждое значение `EApiCategories` ссылается на список управляемых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="0fc70-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="0fc70-126">Перечисление `EApiCategories` и метод `SetProtectedCategories` напрямую связаны с управляемым классом <xref:System.Security.Permissions.HostProtectionAttribute>, который используется для обозначения управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описанным в `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="0fc70-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="0fc70-127">Дополнительные сведения см. в разделе <xref:System.Security.Permissions.HostProtectionAttribute> и перечисление <xref:System.Security.Permissions.HostProtectionResource>, которое непосредственно соответствует `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="0fc70-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc70-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0fc70-128">Requirements</span></span>  
 <span data-ttu-id="0fc70-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc70-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc70-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0fc70-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0fc70-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0fc70-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fc70-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc70-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc70-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0fc70-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="0fc70-134">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="0fc70-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="0fc70-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0fc70-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0fc70-136">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="0fc70-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
