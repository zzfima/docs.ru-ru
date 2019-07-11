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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f6dc1254261197583f2369587a61b5e179d760b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779641"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="0e474-102">Метод ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="0e474-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="0e474-103">Указывает, какие категории управляемых типов и членов должен блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="0e474-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e474-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e474-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e474-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e474-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="0e474-106">[in] Сочетание [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) значения, указывающие, какие категории управляемых типов и членов должен блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="0e474-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e474-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e474-107">Return Value</span></span>  
  
|<span data-ttu-id="0e474-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e474-108">HRESULT</span></span>|<span data-ttu-id="0e474-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0e474-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e474-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e474-110">S_OK</span></span>|<span data-ttu-id="0e474-111">`SetProtectedCategories` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0e474-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="0e474-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e474-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e474-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0e474-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e474-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e474-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e474-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0e474-115">The call timed out.</span></span>|  
|<span data-ttu-id="0e474-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e474-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e474-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0e474-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e474-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e474-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e474-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0e474-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e474-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e474-120">E_FAIL</span></span>|<span data-ttu-id="0e474-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0e474-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e474-122">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="0e474-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e474-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0e474-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e474-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e474-124">Remarks</span></span>  
 <span data-ttu-id="0e474-125">Каждый `EApiCategories` значение ссылается на список управляемых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="0e474-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="0e474-126">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемый <xref:System.Security.Permissions.HostProtectionAttribute> класс, который используется для пометки управляемых типов и членов, которые предоставляют возможности, соответствующие категории, описанные по `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="0e474-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="0e474-127">Дополнительные сведения см. в разделе <xref:System.Security.Permissions.HostProtectionAttribute> и <xref:System.Security.Permissions.HostProtectionResource> перечисления, который напрямую соответствует идентификатору `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="0e474-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e474-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0e474-128">Requirements</span></span>  
 <span data-ttu-id="0e474-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e474-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e474-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e474-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e474-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e474-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e474-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e474-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e474-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0e474-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="0e474-134">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="0e474-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="0e474-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0e474-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0e474-136">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="0e474-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
