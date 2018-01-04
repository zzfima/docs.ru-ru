---
title: "Метод ICLRHostProtectionManager::SetProtectedCategories"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetProtectedCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0971e93f02420966d6561c5b7d4dce8b75e222fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="63912-102">Метод ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="63912-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="63912-103">Указывает, какие категории управляемых типов и членов должны блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="63912-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63912-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63912-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63912-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63912-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="63912-106">[in] Сочетание [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) значений, указывающее, какие категории управляемых типов и членов должны блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="63912-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63912-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="63912-107">Return Value</span></span>  
  
|<span data-ttu-id="63912-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63912-108">HRESULT</span></span>|<span data-ttu-id="63912-109">Описание</span><span class="sxs-lookup"><span data-stu-id="63912-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63912-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="63912-110">S_OK</span></span>|<span data-ttu-id="63912-111">`SetProtectedCategories`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="63912-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="63912-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63912-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63912-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="63912-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63912-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63912-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63912-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="63912-115">The call timed out.</span></span>|  
|<span data-ttu-id="63912-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63912-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63912-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="63912-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63912-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63912-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63912-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="63912-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63912-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63912-120">E_FAIL</span></span>|<span data-ttu-id="63912-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="63912-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63912-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="63912-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63912-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63912-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63912-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="63912-124">Remarks</span></span>  
 <span data-ttu-id="63912-125">Каждый `EApiCategories` значение ссылается на список управляемых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="63912-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="63912-126">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемом <xref:System.Security.Permissions.HostProtectionAttribute> класс, который используется для пометки управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описываемого `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="63912-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="63912-127">Дополнительные сведения см. в разделе <xref:System.Security.Permissions.HostProtectionAttribute> и <xref:System.Security.Permissions.HostProtectionResource> перечисления, который напрямую соответствует идентификатору `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="63912-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63912-128">Требования</span><span class="sxs-lookup"><span data-stu-id="63912-128">Requirements</span></span>  
 <span data-ttu-id="63912-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63912-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63912-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63912-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63912-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63912-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63912-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63912-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63912-133">См. также</span><span class="sxs-lookup"><span data-stu-id="63912-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="63912-134">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="63912-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="63912-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="63912-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="63912-136">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="63912-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
