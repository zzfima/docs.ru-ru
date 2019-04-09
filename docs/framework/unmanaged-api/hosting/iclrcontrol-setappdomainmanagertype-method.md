---
title: Метод ICLRControl::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eacd3802c51cb6ccf3f7ba874c75a2d2774439d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091197"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="f868a-102">Метод ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="f868a-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="f868a-103">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="f868a-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f868a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f868a-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f868a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f868a-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="f868a-106">[in] Имя сборки, в котором запрошенный тип, производный от <xref:System.AppDomainManager> реализуется.</span><span class="sxs-lookup"><span data-stu-id="f868a-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="f868a-107">[in] Имя типа, реализованные в `pwzAppDomainManagerAssembly` параметр, который реализует возможности <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="f868a-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f868a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f868a-108">Return Value</span></span>  
  
|<span data-ttu-id="f868a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f868a-109">HRESULT</span></span>|<span data-ttu-id="f868a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f868a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f868a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f868a-111">S_OK</span></span>|<span data-ttu-id="f868a-112">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="f868a-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="f868a-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f868a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f868a-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f868a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f868a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f868a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f868a-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f868a-116">The call timed out.</span></span>|  
|<span data-ttu-id="f868a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f868a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f868a-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f868a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f868a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f868a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f868a-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f868a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f868a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f868a-121">E_FAIL</span></span>|<span data-ttu-id="f868a-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f868a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f868a-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="f868a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f868a-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f868a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f868a-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f868a-125">Requirements</span></span>  
 <span data-ttu-id="f868a-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f868a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f868a-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f868a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f868a-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f868a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f868a-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f868a-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f868a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f868a-130">See also</span></span>

- [<span data-ttu-id="f868a-131">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f868a-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f868a-132">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="f868a-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
