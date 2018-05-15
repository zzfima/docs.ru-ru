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
ms.openlocfilehash: be778fed910b2cbdbf5e9ae7754abae437ef6bec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="29ae1-102">Метод ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="29ae1-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="29ae1-103">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="29ae1-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ae1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29ae1-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29ae1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29ae1-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="29ae1-106">[in] Имя сборки, в которой запрошенного типа производным от <xref:System.AppDomainManager> реализуется.</span><span class="sxs-lookup"><span data-stu-id="29ae1-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="29ae1-107">[in] Имя типа, реализованные в `pwzAppDomainManagerAssembly` параметр, который реализует возможности <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="29ae1-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29ae1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="29ae1-108">Return Value</span></span>  
  
|<span data-ttu-id="29ae1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29ae1-109">HRESULT</span></span>|<span data-ttu-id="29ae1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="29ae1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29ae1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="29ae1-111">S_OK</span></span>|<span data-ttu-id="29ae1-112">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="29ae1-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="29ae1-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29ae1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29ae1-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="29ae1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29ae1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29ae1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29ae1-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="29ae1-116">The call timed out.</span></span>|  
|<span data-ttu-id="29ae1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29ae1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29ae1-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="29ae1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29ae1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29ae1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29ae1-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="29ae1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29ae1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29ae1-121">E_FAIL</span></span>|<span data-ttu-id="29ae1-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="29ae1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="29ae1-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="29ae1-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29ae1-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="29ae1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29ae1-125">Требования</span><span class="sxs-lookup"><span data-stu-id="29ae1-125">Requirements</span></span>  
 <span data-ttu-id="29ae1-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29ae1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ae1-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29ae1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29ae1-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29ae1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29ae1-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ae1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ae1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="29ae1-130">See Also</span></span>  
 [<span data-ttu-id="29ae1-131">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="29ae1-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="29ae1-132">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="29ae1-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
